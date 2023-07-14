---
share: true
alias: "Music"
type: "campaign"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
---

# Things to Sort

# Quests
## Main
### Active
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest")
    .where(page => page["sub-type"] == "main")
    .where(page => page["status"] == "active");
let campaign = dv.current().file;
for (let page of pages)
{
	if(page["campaign"].path == campaign.path)
		result += '- ' + page.file.link + '\n';
}
    
dv.el("div", result)
```

### Available
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest")
    .where(page => page["sub-type"] == "main")
    .where(page => page["status"] == "available");
let campaign = dv.current().file;
for (let page of pages)
{
	if(page["campaign"].path == campaign.path)
		result += '- ' + page.file.link  + '\n';
}
    
dv.el("div", result)
```
## Major
### Active
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest")
    .where(page => page["sub-type"] == "major")
    .where(page => page["status"] == "active");
    
let campaign = dv.current().file;
for (let page of pages)
{
	if (page["campaign"] != undefined)
	{
		if(page["campaign"].path == campaign.path) 
		 {
			result += '- ' + page.file.link + '\n';
		 }
	}
}
	
    
dv.el("div", result)
```
### Available
```dataviewjs
let result = "";

let pages = dv.pages()
    .where(page => page["type"] == "quest")
    .where(page => page["sub-type"] == "major")
    .where(page => page["status"] == "available");
    
let campaign = dv.current().file;
for (let page of pages)
{
	if (page["campaign"] != undefined)
	{
		if(page["campaign"].path == campaign.path)
		 {
			result += '- ' + page.file.link + '\n';
		 }
	}
}
	
    
dv.el("div", result)
```
## Minor
### Active
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest")
    .where(page => page["sub-type"] == "minor")
    .where(page => page["status"] == "active");
let campaign = dv.current().file;
for (let page of pages)
{
	if(page["campaign"] != undefined && page["campaign"].path == campaign.path)
		result += '- ' + page.file.link + '\n';
}
    
dv.el("div", result)
```
### Available
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest")
    .where(page => page["sub-type"] == "minor")
    .where(page => page["status"] == "available");
let campaign = dv.current().file;
for (let page of pages)
{
	if(page["campaign"] != undefined && page["campaign"].path == campaign.path)
		result += '- ' + page.file.link + '\n';
}
    
dv.el("div", result)
```
# Aspects
[ 00 - Routines](05%20-%20Music/00%20-%20Routines/00%20-%20Routines.md)
[01 - Records](./01%20-%20Records.md)
[02 - Writing](./02%20-%20Writing.md)
[03 - Playing Bass](./03%20-%20Playing%20Bass.md)
[04 - Playing Drums](./04%20-%20Playing%20Drums.md)
[05 - Playing Piano](./05%20-%20Playing%20Piano.md)
[06 - Singing](./06%20-%20Singing.md)
[07 - Playing Guitar](./07%20-%20Playing%20Guitar.md)
[08 - Transcription](./08%20-%20Transcription.md)
# Things I've Done
- [x] New Aspect: Transcription 🥄0 ⏫ ➕ 2023-04-11 ⏳ 2023-04-11 ✅ 2023-04-11
- [x] New Aspect: Bass Playing ⏫ ➕ 2023-03-27 ✅ 2023-03-27
- [x] New Aspect: Playing Drums ⏫ ➕ 2023-03-27 ✅ 2023-03-27
- [x] New Aspect: Playing Piano ⏫ ➕ 2023-03-27 ✅ 2023-03-29
- [x] New Aspect: Singing ⏫ ➕ 2023-03-27 ✅ 2023-03-29
- [x] New Aspect: Playing Guitar ⏫ ➕ 2023-03-27 ✅ 2023-03-29
- [x] New Quest: [Release an Album](./Release%20an%20Album.md) 🛫 2023-03-20 ✅ 2023-03-20
- [x] New Aspect: Records ✅ 2023-03-20
- [x] New Aspect: Writing ✅ 2023-03-20
- [x] add an [Album Wish List](./Album%20Wish%20List.md) ➕ 2023-03-02 ✅ 2023-03-02
- [x] add MF Doom's *The Mouse & The Mask* album record ➕ 2023-03-02 ✅ 2023-03-02
- [-] Listen to an episode of [No Dogs in Space](No%20Dogs%20in%20Space.md) #podcast #fun #music #lpotl #history 🥄+2  📆2023-07-16