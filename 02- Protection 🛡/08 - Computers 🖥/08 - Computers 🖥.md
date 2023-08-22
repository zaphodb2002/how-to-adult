---
share: true
type: "aspect"
created: NaN 
modified: NaN
---

# Things to Do
- [ ] New Quest: Set up a new computer for Mom #LMS #bureaucracy 🍅1 🥄1 🆙+2
- [ ] New Quest: Set up a Proxmox server #LMS #bureaucracy 🍅1 🥄1 🆙+2
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
- [x] Set up the second monitor #tech 🥄3 ✅ 2023-07-03
