---
share: true
alias: "Visual Arts"
type: "campaign"
created: NaN 
modified: NaN
---

# Things to Sort
- [ ] Draw for 5 minutes #art #practice #habit #challenge  📆2023-07-16
- [ ] Fill a sketchbook page #art #practice #relaxing 🥄+5 📆2023-07-16
- [f] Look at your previous drawings in your sketchbook for 5 minutes #art #littlePush #challenge 🥄+2 📅 2023-07-13

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
[ 00 - Routines](./00%20-%20Routines.md)
[01 - Cartooning](./01%20-%20Cartooning.md)
[02 - Pixel Art](./02%20-%20Pixel%20Art.md)
[03 - 3D Modeling](./03%20-%203D%20Modeling.md)

# Things I've Done
- [x] New Aspect: 3D Modeling 🥄1 ⏫ ➕ 2023-04-15 ⏳ 2023-04-17 ✅ 2023-04-15
- [x] New Aspect: Cartooning ⏫ ➕ 2023-03-31 ✅ 2023-04-04
- [x] New Aspect: Pixel Art ⏫ ➕ 2023-03-31 ✅ 2023-04-04
- [f] Look at your previous drawings in your sketchbook for 5 minutes #art #littlePush #challenge 🥄+2 📆2023-07-12