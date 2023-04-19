---
share: true
alias: "Psychonautics"
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
    .where(page => page["type"] == "quest")
    .where(page => page["sub-type"] == "main");
let campaign = "Psychonautics";
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
let campaign = "Psychonautics";
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
let campaign = "Psychonautics";
for (let page of pages)
{
	if(page["status"] == "available" && page["campaign"] == campaign)
		result += '- ' + page.file.link + ": " + page["status"] + ' for [' + page"aspect"]('%20+%20page%22aspect%22.md)\n';
}
    
dv.el("div", result)
```

# Aspects
[00 - Routines](./00%20-%20Routines.md)
[01 - Research](./01%20-%20Research.md)
[02 - Cannabis](./02%20-%20Cannabis.md)
[03 - Psilocybin](./03%20-%20Psilocybin.md)
[04 - Mescaline](./04%20-%20Mescaline.md)

# Things I've Done
- [x] New Aspect: Research ⏫ ➕ 2023-03-27 ✅ 2023-03-29
- [x] New Aspect: Mescaline ⏫ ➕ 2023-03-27 ✅ 2023-03-29
- [x] New Aspect: Psilocybin ⏫ ➕ 2023-03-27 ✅ 2023-03-29
- [x] New Aspect: Routines ⏫ ➕ 2023-03-27 ✅ 2023-03-29
- [x] New Aspect: Cannabis ✅ 2023-03-20