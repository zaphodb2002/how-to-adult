---
share: true
type: "aspect"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
---

# Things to Do

# Summary

# Routines
```dataviewjs
let folder = dv.current().file.folder;
let pages = await dv.pages('"'+folder+'"')
		.where(page => page.file.tags.includes('#routine')).file.link

dv.list(pages)
```
# Quests
```dataviewjs
let folder = dv.current().file.folder;
let pages = await dv.pages('"'+folder+'"')
		.where(page => page.file.tags.includes('#quest')).file.link

dv.list(pages)
```
# Things I've Done