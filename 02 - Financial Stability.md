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
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest");
let campaign = "Financial Stability";
for (let page of pages)
{
	if(page["status"] == "main" && page["campaign"] == campaign)
		result += '- ' + page.file.link + ": " + page["status"] + '\n';
}
    
dv.el("div", result)
```

## Active
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest");
let campaign = "Financial Stability";
for (let page of pages)
{
	if(page["status"] == "active" && page["campaign"] == campaign)
		result += '- ' + page.file.link + ": " + page["status"] + ' for [' + page"aspect"]('%20+%20page%22aspect%22.md)\n';
}
    
dv.el("div", result)
```

## Available
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest");
let campaign = "Financial Stability";
for (let page of pages)
{
	if(page["status"] == "available" && page["campaign"] == campaign)
		result += '- ' + page.file.link + ": " + page["status"] + ' for [' + page"aspect"]('%20+%20page%22aspect%22.md)\n';
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
- [x] ⏫ New Mission: [Create a simple project on github](./Create%20a%20simple%20project%20on%20github.md) for [Make a Portfolio Website](./Make%20a%20Portfolio%20Website.md) 🛫 2023-03-14 ✅ 2023-03-18
	- useful for [Resume](./Resume.md)
- [x] ⏫  New Mission: Get "added" as a status in Obsidian Tasks accepted in a PR 🛫 2023-03-12 ✅ 2023-03-18
	- 2023-03-18 19:59 Duplicate of another task over in [05 - Tools](./05%20-%20Tools.md) that also needs to be sorted, closing this one
- [x] ⏫ New Aspect: [Employment](Employment.md) ➕ 2023-03-08 📅 2023-03-08 ✅ 2023-03-08
- [x] New Aspect: [Digital Footprint](Digital%20Footprint.md) for [Financial Stability](Financial%20Stability.md) ➕ 2023-03-03 ✅ 2023-03-08