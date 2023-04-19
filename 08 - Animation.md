---
share: true
alias: "Animation"
type: "campaign"
created: NaN 
modified: NaN
---

# Things to Sort


# Quests
## Main
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest");
let campaign = "undefined";
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
let campaign = "undefined";
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
let campaign = "undefined";
for (let page of pages)
{
	if(page["status"] == "available" && page["campaign"] == campaign)
		result += '- ' + page.file.link + ": " + page["status"] + ' for [' + page"aspect"]('%20+%20page%22aspect%22.md)\n';
}
    
dv.el("div", result)
```
# Aspects
[ 00 - Routines](08%20-%20Animation/00%20-%20Routines/00%20-%20Routines.md)
[01 - Cartooning](./01%20-%20Cartooning.md)
[02 - Pixel Art](./02%20-%20Pixel%20Art.md)
[03 - 3D Modeling](./03%20-%203D%20Modeling.md)

# Things I've Done
- [x] New Aspect: 3D Modeling 🥄1 ⏫ ➕ 2023-04-15 ⏳ 2023-04-17 ✅ 2023-04-15
- [x] New Aspect: Cartooning ⏫ ➕ 2023-03-31 ✅ 2023-04-04
- [x] New Aspect: Pixel Art ⏫ ➕ 2023-03-31 ✅ 2023-04-04
