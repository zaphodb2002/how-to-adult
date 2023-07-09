---
share: true
alias: "Personal Wellness"
type: "campaign"
created:  <%+ tp.file.creation_date() %>
modified:  <%+ tp.file.last_modified_date() %>
---
#PersonalWellness 
# Things to Sort
- [ ] Verify CVS got my renewal ➕ 2023-07-07 ⏫ ⏳ 2023-07-10 

- [ ] Attend July 20th 12:45 Ramona Palomar Health Doc Appt #healthy #doctor #adhd #meds #myBack #pain 🥄20 ➕ 2023-07-07 ⏫ ⏳ 2023-07-20 




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
[ 00 - Routines](01%20-%20Personal%20Wellness/00%20-%20Routines/00%20-%20Routines.md)
[01 - Environment](./01%20-%20Environment.md)
[02 - ADHD](./02%20-%20ADHD.md)
[03 - Ethics](./03%20-%20Ethics.md)
[04 - Food](./04%20-%20Food.md)
[05 - People](./05%20-%20People.md)
[06 - Fishkeeping](./06%20-%20Fishkeeping.md)
[07 - Emotions](./07%20-%20Emotions.md)
[08 - Pets](./08%20-%20Pets.md)
[09 - Personal Aesthetic](./09%20-%20Personal%20Aesthetic.md)
# Goals
- Like who I am

# Things I've Done
- [x] New Aspect: Pets #bureaucracy  🥄1 ⏫ ➕ 2023-04-18 ⏳ 2023-04-19 ✅ 2023-04-19
- [x] New Aspect: Emotions 🥄1 ⏫ ➕ 2023-04-13 ⏳ 2023-04-17 ✅ 2023-04-14

- [x] New Aspect: Fishkeeping ⏫ ➕ 2023-04-05 ⏳ 2023-04-17 ✅ 2023-04-10
- [x] New Aspect: People ⏫ ➕ 2023-03-29 ✅ 2023-03-30
- [x] New Aspect: Ethics ✅ 2023-03-18
- [x] New Aspect: Philosophy ➕ 2023-03-13 ✅ 2023-03-14
- [x] New Quest: [Just The One Rule](./Just%20The%20One%20Rule.md) ➕ 2023-03-10 ✅ 2023-03-16
- [x] ⏫ New Quest: [Live Deliberately](./Live%20Deliberately.md) ➕ 2023-03-10 📅 2023-03-11 ✅ 2023-03-13
- [x] ⏫ New Aspect: [ADHD](ADHD.md) ➕ 2023-03-08 ✅ 2023-03-08