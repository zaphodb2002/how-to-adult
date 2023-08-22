---
share: true
type: "knowledge"
created: NaN 
modified: NaN
---
# Summary

[GitHub](https://github.com/Zylann/godot_voxel)
[Official Documentation is here](https://voxel-tools.readthedocs.io/en/latest/)


# What is a Voxel?
- "Voxel" is short for "Volumetric Element" in the same way "Pixel" is short for "Picture Element".
- Span 3D grid instead of 2D
- Smallest element in system
- Contains data about itself:
	- Type
	- density (or signed distance)
	- Color
	- Material
	- etc...
## Generating Voxels
- implement `VoxelGenerator` to generate voxel data
	- `VoxelGeneratorNoise2D` = Height maps from noise
	- `VoxelGeneratorNoise` = "Spongy" world from 3D noise (tunnels and overhangs)
	- `VoxelGeneratorFlat` = Flat plane
	- `VoxelGeneratorGraph` = Combine operations using graphs (3D VisualShader) for complex jobs
	- `VoxelGeneratorScript` = Use a script. Probably should be C# or GDExtension
	- Others, anything derived from `VoxelGenerator` (including custom classes)
## Storing Voxels
- Implement `VoxelBuffer` to store Voxel data
	- uses multiple channels for information
		- `TYPE` = an ID to identify the voxel
		- `SDF` = Signed distance field, for smooth terrain
		- `COLOR` = Color info. Can be compressed RGBA or palette index
		- others
	- channels have configurable bit depth to 64 bit
## Saving Voxels to Disk
- Implement `VoxelStream` to save to (and load from) disk
- can be Region files or DB connection
## Turning Voxels into meshes
- Implement `VoxelMesher` to draw the meshes from voxel data
	- `VoxelMesherCubes` = uses `COLOR` channel to produce cubes
	- `VoxelMesherBlocky` = uses `TYPE` channel to produce cubes (or any custom shape)
	- `VoxelMesherTransvoxel` = uses `SDF` channel to produce smooth surface based on TransVoxel algorithm. Also allows LOD.
	- `VoxelMesherDMC` = uses `SDF` channel to produce smooth surface based on Dual Marching Cubes algorithm. No longer maintained.
## How it works in Godot
- Use `VoxelTerrain` Nodes for terrain
	- `VoxelTerrain` = simple grid. Handles Block (16 x 16 x 16 voxels, called chunk in Minecraft) loading and unloading. No LOD, so view distance limited.
	- `VoxelLODTerrain` = octree. allows LOD, but only supports smooth surfaces and has other limitations.
- Use `VoxelTool` to allow in game editing of voxels.
	- `get_voxel_tool()` methods
	- allows setting individual voxels directly or blend shapes to dig around. Also uses `TYPE`, `SDF`, `COLOR` channels
- Attach a `VoxelViewer` node to either the player or camera, this will determine where the voxels load

# Terrain Types

## Common Properties
- derived from `VoxelNode`, which contains:
	- `["stream"]`= a `VoxelStream`
	- `["generator"]` = a `VoxelGenerator`
	- `["mesher"]` = a `VoxelMesher`
- Collisions are physics or raycast based
	- behave like static body
	- built with the mesh so only rebuilt when edited

## Blocky Terrain
#TODO
## Smooth Terrain
- Use `VoxelMesherTransvoxel`
- Uses the `SDF` channel
### Signed distance fields
 - represents the distance to the closest surface
 - if above surface, positive number. if below, negative. thus, signed
 - surface is defined by all points with SDF == 0. called `isolevel`
 - commonly used in raymarching shaders to define volumes. used here in TransVoxel algorithm.

#### Technical Explanation
```
if distance(center, position) < radius:
  voxel = 1
else:
  voxel = 0
```

creates in 2D:
![Pixel Circle!](https://voxel-tools.readthedocs.io/en/latest/images/sdf_example_blocky.webp)

creates in 3D:
![Chunky Voxel Sphere!](https://voxel-tools.readthedocs.io/en/latest/images/sdf_sphere_blocky.webp)

---

```
voxel = distance(origin, position) - radius
```

creates in 2D:
![Gradient](https://voxel-tools.readthedocs.io/en/latest/images/sdf_example_true.webp)

creates in 3D:
![Smooth Voxel Sphere](https://voxel-tools.readthedocs.io/en/latest/images/sdf_sphere_smooth.webp)

---
after clamping and scaling for optimization in 2D:
![clamped to the surface of the circle](https://voxel-tools.readthedocs.io/en/latest/images/sdf_example_clamped.webp)

Because we don't care how far the top is from the sky or whatever, just how far it is from the stuff that's close, and we don't care about the insides either so just average that shit out

---

- engine uses 8 or 16 bit integers clamped and scaled to `-1 , 1`
- means that before storing SDF in `VoxelBuffer` we scale by 0.1 (or smaller when using 16 bit).
	- Tweak this if you want longer / shorter gradients at cost of performance

### TransVoxel
https://transvoxel.org/

#### Smooth Stitches in Vertex Shader
- meshes produced by `VoxelMesherTransVoxel` contain extra information in their `CUSTOM0` attribute 
- Create and set up a `ShaderMaterial` on terrain, and integrate this snippet:
```
// This is recognized and assigned automatically by the voxel engine
uniform int u_transition_mask;

float get_transvoxel_secondary_factor(int idata) {
  int cell_border_mask = idata & 63; // Which sides the cell is touching
  int vertex_border_mask = (idata >> 8) & 63; // Which sides the vertex is touching
  // If the vertex is near a side where there is a low-resolution neighbor,
  // move it to secondary position
  int m = u_transition_mask & cell_border_mask;
  float t = float(m != 0);
  // If the vertex lies on one or more sides, and at least one side has no low-resolution neighbor,
  // don't move the vertex.
  t *= float((vertex_border_mask & ~u_transition_mask) == 0);
  return t;
}

vec3 get_transvoxel_position(vec3 vertex_pos, vec4 fdata) {
  int idata = floatBitsToInt(fdata.a);

  // Move vertices to smooth transitions
  float secondary_factor = get_transvoxel_secondary_factor(idata);
  vec3 secondary_position = fdata.xyz;
  vec3 pos = mix(vertex_pos, secondary_position, secondary_factor);

  // If the mesh combines transitions and the vertex belongs to a transition,
  // when that transition isn't active we change the position of the vertices so
  // all triangles will be degenerate and won't be visible.
  // This is an alternative to rendering them separately,
  // which has less draw calls and less mesh resources to create in Godot.
  // Ideally I would tweak the index buffer like LOD does but Godot does not
  // expose anything to use it that way.
  int itransition = (idata >> 16) & 0xff; // Is the vertex on a transition mesh?
  float transition_cull = float(itransition == 0 || (itransition & u_transition_mask) != 0);
  pos *= transition_cull;

  return pos;
}

void vertex() {
  VERTEX = get_transvoxel_position(VERTEX, CUSTOM0);
  //...
}
```

https://github.com/Zylann/godot_voxel/issues/2 for details