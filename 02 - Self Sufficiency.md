---
share: true
alias: "Financial Stability"
type: "campaign"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
---

# Things to Sort
- [x] New Aspect: 3D Printing #bureaucracy 🥄1 ⏫ ➕ 2023-06-01 ⏳ 2023-06-05 ✅ 2023-06-01
- [x] New Aspect: Routines ⏫ ➕ 2023-03-29 ✅ 2023-03-31
- [x] New Aspect: Records ⏫ ➕ 2023-03-29 ✅ 2023-03-31
- [x] New Aspect: Automotive ➕ 2023-03-21 ✅ 2023-03-24
- [x] ⏫ New Aspect: Tools 🛫 2023-03-20 ✅ 2023-03-20
- [x] ⏫ New Aspect: Construction 🛫 2023-03-10 ✅ 2023-03-18
- [x] ⏫ New Aspect: Gardening ➕ 2023-03-10 ✅ 2023-03-10

- [ ] Worked for a full pomodoro loop #adhd #habit 🥄+5 📆2023-07-14
- [x] Work a pomodoro chunk #work #habit 🥄5 📅 2023-07-14 ✅ 2023-07-14
- [x] Work a pomodoro chunk #work #habit 🥄5 📅 2023-07-14 ✅ 2023-07-14
- [ ] Work a pomodoro chunk #work #habit 🥄5  📆2023-07-14
- [ ] Work a pomodoro chunk #work #habit 🥄5  📆2023-07-14




- [x] Worked for a full pomodoro loop #adhd #habit 🥄+5 📅 2023-07-13 ✅ 2023-07-13
- [x] Work a pomodoro chunk #work #habit 🥄5 📅 2023-07-13 ✅ 2023-07-13
- [x] Work a pomodoro chunk #work #habit 🥄5 📅 2023-07-13 ✅ 2023-07-13
- [x] Work a pomodoro chunk #work #habit 🥄5 📅 2023-07-13 ✅ 2023-07-13
- [x] Work a pomodoro chunk #work #habit 🥄5 📅 2023-07-13 ✅ 2023-07-13


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
[01 - Financial Stability](./01%20-%20Financial%20Stability.md)
[02 - Computers](./02%20-%20Computers.md)
[03 - Digital Footprint](03%20-%20Digital%20Footprint.md)
[04 - Expenses](04%20-%20Expenses.md)

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
- [x] ⏫ New Aspect: [01 - Financial Stability](./01%20-%20Financial%20Stability.md) #bureaucracy 🥄+1 ➕ 2023-03-08 📅 2023-03-08 ✅ 2023-03-08
- [x] New Aspect: [03 - Digital Footprint](03%20-%20Digital%20Footprint.md) #bureaucracy 🥄+1 ➕ 2023-03-03 ✅ 2023-03-08
- [x] Check email #bureaucracy #communication 🥄3 ⏫ 📅 2023-07-14 ✅ 2023-07-14
- [x] Apply for a job #NotFun #tedious   🥄2 ⏫ 📅 2023-07-14 ✅ 2023-07-14
- [x] Apply for a job #NotFun #tedious 🥄2 📅 2023-07-16 ✅ 2023-07-12
- [x] Apply for a job #NotFun #tedious  🥄2 📅 2023-07-16 ✅ 2023-07-12
- [x] Apply for a job #NotFun #tedious  🥄2 📅 2023-07-16 ✅ 2023-07-12
- [x] Apply for a job #NotFun #tedious  🥄2 📅 2023-07-16 ✅ 2023-07-12
- [f] Out of bed before 0700 #habit #depression 🥄+10 📅 2023-07-12
- [f] Out of bed before 0800 #habit #depression 🥄+5 📅 2023-07-12
- [x] Put pants on #habit #depression 🥄+5 📅 2023-07-12 ✅ 2023-07-12
- [-] Put on shoes and socks #habit #depression 🥄+5 📅 2023-07-12
- [f] Put on watch #habit #communication #BePrepared 🥄+5 📅 2023-07-12
- [x] Worked for a full pomodoro loop #adhd #habit 🥄+5 📅 2023-07-12 ✅ 2023-07-12