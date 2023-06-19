---
share: true
alias: "Cinema"
type: "campaign"
created: NaN 
modified: NaN
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
# Summary
# Aspects
[00 - Routines](./00%20-%20Routines.md)
[01 - Records](./01%20-%20Records.md)
[02 - Tools](./02%20-%20Tools.md)
[03 - Research](./03%20-%20Research.md)

# Things I've Done
- [x] New Aspect: Research 🥄0 ➕ 2023-04-11 ⏳ 2023-04-11 ✅ 2023-04-11
- [x] New Aspect: Tools 🥄0 ⏫ ➕ 2023-04-11 ⏳ 2023-04-11 ✅ 2023-04-11
- [x] New Aspect: Records ⏫ ➕ 2023-04-04 ⏳ 2023-04-17 ✅ 2023-04-10
- [x] New Aspect: Routines ⏫ ➕ 2023-04-04 ⏳ 2023-04-17 ✅ 2023-04-10
