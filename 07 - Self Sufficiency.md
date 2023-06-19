---
share: true
alias: "Self Sufficiency"
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
[00 - Routines](./00%20-%20Routines.md)
[01 - Records](./01%20-%20Records.md)
[02 - Gardening](./02%20-%20Gardening.md)
[03 - Automotive](./03%20-%20Automotive.md)
[04 - Construction](./04%20-%20Construction.md)
[05 - Tools](./05%20-%20Tools.md)

# Summary
[Julian, CA](./Julian,%20CA.md)

# Things I've Done
- [x] New Aspect: 3D Printing #bureaucracy 🥄1 ⏫ ➕ 2023-06-01 ⏳ 2023-06-05 ✅ 2023-06-01
- [x] New Aspect: Routines ⏫ ➕ 2023-03-29 ✅ 2023-03-31
- [x] New Aspect: Records ⏫ ➕ 2023-03-29 ✅ 2023-03-31
- [x] New Aspect: Automotive ➕ 2023-03-21 ✅ 2023-03-24
- [x] ⏫ New Aspect: Tools 🛫 2023-03-20 ✅ 2023-03-20
- [x] ⏫ New Aspect: Construction 🛫 2023-03-10 ✅ 2023-03-18
- [x] ⏫ Get a plan for the garden going ➕ 2023-03-10 ✅ 2023-03-13
- [x] ⏫ New Aspect: Gardening ➕ 2023-03-10 ✅ 2023-03-10
- [x] ⏫ New Quest: [A Man's Only As Good As His Tools](./A%20Man's%20Only%20As%20Good%20As%20His%20Tools.md) ➕ 2023-03-10 ✅ 2023-03-10
