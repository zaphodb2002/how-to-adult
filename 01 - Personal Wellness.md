---
share: true
alias: "Personal Wellness"
type: "campaign"
created:  <%+ tp.file.creation_date() %>
modified:  <%+ tp.file.last_modified_date() %>
---
#PersonalWellness 
# Things to Sort

- [ ] Journal Entry #mindfulness #writing 🥄5 📆2023-07-16

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

# Goals
- Like who I am

# Things I've Done
- [x] New Aspect: Pets #bureaucracy  🥄1 ⏫ ➕ 2023-04-18 ⏳ 2023-04-19 ✅ 2023-04-19
- [x] New Aspect: Emotions 🥄1 ⏫ ➕ 2023-04-13 ⏳ 2023-04-17 ✅ 2023-04-14
- [x] New Aspect: Fishkeeping ⏫ ➕ 2023-04-05 ⏳ 2023-04-17 ✅ 2023-04-10
- [x] New Aspect: People ⏫ ➕ 2023-03-29 ✅ 2023-03-30
- [x] New Aspect: Reason ➕ 2023-03-13 ✅ 2023-03-14

- [x] ⏫ New Aspect: [ADHD](ADHD.md) ➕ 2023-03-08 ✅ 2023-03-08





