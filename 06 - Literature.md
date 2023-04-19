---
share: true
alias: "Literature"
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
# Summary
[Book Wish List](./Book%20Wish%20List.md)
[Bookshelf](./Bookshelf.md)
# Aspects
[00 - Records](./00%20-%20Records.md)
[01 - Reading Fiction](./01%20-%20Reading%20Fiction.md)
[02 - Writing Fiction](./02%20-%20Writing%20Fiction.md)
[03 - Reading Non-Fiction](./03%20-%20Reading%20Non-Fiction.md)
[04 - Writing Non-Fiction](./04%20-%20Writing%20Non-Fiction.md)
[05 - Reading Poetry](./05%20-%20Reading%20Poetry.md)
[06 - Writing Poetry](./06%20-%20Writing%20Poetry.md)

# Goals

# Things I've Done
- [x] New Aspect: Writing Poetry ⏫ ➕ 2023-03-29 ✅ 2023-03-30
- [x] New Aspect: Writing Non-Fiction ⏫ ➕ 2023-03-29 ✅ 2023-03-30
- [x] New Aspect: Writing Fiction ⏫ ➕ 2023-03-29 ✅ 2023-03-30
- [x] New Aspect: Reading Poetry ⏫ ➕ 2023-03-29 ✅ 2023-03-30
- [x] New Aspect: Reading Non-Fiction ⏫ ➕ 2023-03-29 ✅ 2023-03-30
- [x] New Aspect: Reading Fiction ⏫ ➕ 2023-03-29 ✅ 2023-03-30
 - [x] New Aspect: Records ✅ 2023-03-20
- [x] Add a [Book Wish List](./Book%20Wish%20List.md) ➕ 2023-03-02 📅 2023-03-09 ✅ 2023-03-02
- [x] Add *Notes from the Underground* to book wish list ➕ 2023-03-02 ✅ 2023-03-02