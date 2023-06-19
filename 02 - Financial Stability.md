---
share: true
alias: "Financial Stability"
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
[ 00 - Routines](02%20-%20Financial%20Stability/00%20-%20Routines/00%20-%20Routines.md)
[01 - Employment](./01%20-%20Employment.md)
[02 - Skills](./02%20-%20Skills.md)
[03 - Digital Footprint](./03%20-%20Digital%20Footprint.md)
[04 - Expenses](./04%20-%20Expenses.md)

# Goals
- Pay off the house
- Pay off the solar
- Buy 10+ acres of land
# Things I've Done
- [x] New Aspect: Expenses 🥄0 ⏫ ➕ 2023-04-11 ⏳ 2023-04-11 ✅ 2023-04-11
 - [x] New Aspect: Skills ✅ 2023-03-20
- [x] ⏫ New Mission: [Create a simple project on github](./Create%20a%20simple%20project%20on%20github.md) for [Make a Portfolio Website](./Make%20a%20Portfolio%20Website.md) #bureaucracy 🥄+1 🛫 2023-03-14 ✅ 2023-03-18
	- useful for [Resume](./Resume.md)
- [x] ⏫  New Mission: Get "added" as a status in Obsidian Tasks accepted in a PR #bureaucracy 🥄+1 🛫 2023-03-12 ✅ 2023-03-18
	- 2023-03-18 19:59 Duplicate of another task over in another note that also needs to be sorted, closing this one
- [x] ⏫ New Aspect: [01 - Employment](./01%20-%20Employment.md) #bureaucracy 🥄+1 ➕ 2023-03-08 📅 2023-03-08 ✅ 2023-03-08
- [x] New Aspect: [03 - Digital Footprint](./03%20-%20Digital%20Footprint.md) #bureaucracy 🥄+1 ➕ 2023-03-03 ✅ 2023-03-08