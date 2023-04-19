---
share: true
alias: "Video Games"
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
let campaign = "Video Games";
for (let page of pages)
{
	if(page["sub-type"] == "main" && page["campaign"] == campaign && page["status"] == "active")
		result += '- ' + page.file.link + ": " + page["status"] + '\n';
}
    
dv.el("div", result)
```

## Active
```dataviewjs
let result = "";
let pages = dv.pages()
    .where(page => page["type"] == "quest");
let campaign = "Video Games";
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
let campaign = "Video Games";
for (let page of pages)
{
	if(page["status"] == "available" && page["campaign"] == campaign)
		result += '- ' + page.file.link + ": " + page["status"] + ' for [' + page"aspect"]('%20+%20page%22aspect%22.md)\n';
}
    
dv.el("div", result)
```
# Aspects
[00 - Game Development](./00%20-%20Game%20Development.md)
[01 - Game Analysis](./01%20-%20Game%20Analysis.md)
[02 - Game Records](./02%20-%20Game%20Records.md)
[03 - Hardware](./03%20-%20Hardware.md)
[04 - Game Design](./04%20-%20Game%20Design.md)
[05 - Untitled Multiplayer Top Down Game](./05%20-%20Untitled%20Multiplayer%20Top%20Down%20Game.md)
# Goals
- Sell a game on Steam
- Live off the money I make from my games
- 
# Contents
[Game Development Products](./Game%20Development%20Products.md)
# Things I've Done
- [x] New Aspect: Game Design ⏫ ➕ 2023-03-27 ✅ 2023-03-27
- [x] New Aspect: Untitled Multiplayer Top Down Game ⏫ ➕ 2023-03-27 ✅ 2023-03-27
- [x] New Aspect: Hardware 🛫 2023-03-20 ✅ 2023-03-20
- [x] ⏫ New Quest: [Living the Dream](./Living%20the%20Dream.md) ➕ 2023-03-14 ✅ 2023-03-16
- [x] New Mission: [Beginner MonoGame Tutorial](./Beginner%20MonoGame%20Tutorial.md). ➕ 2023-03-14 ✅ 2023-03-14
- [x] ⏫ New Aspect: [Game Analysis](Game%20Analysis.md) ➕ 2023-03-03 📅 2023-03-03 ✅ 2023-03-03
- [x] create record template for video games ➕ 2023-03-01 📅 2023-03-03 ✅ 2023-03-03
	- metadata
	- link to pirate
	- review
	- Analysis (for essays or videos)
- [x] Add record for [Disco Elysium](Disco%20Elysium.md) ➕ 2023-03-01 📅 2023-03-03 ✅ 2023-03-03
- [x] Add record for [The Sims 4](./The%20Sims%204.md) ➕ 2023-03-01 📅 2023-03-03 ✅ 2023-03-03
- [x] Install The Sims 4 on the Deck ➕ 2023-03-01 📅 2023-03-03 ✅ 2023-03-03
- [x] 🔼  create a [Game Wish List](./Game%20Wish%20List.md) ➕ 2023-03-02 📅 2023-03-03 ✅ 2023-03-02
- [x] ⏫  Create a list of [Games to Review](./Games%20to%20Review.md) ➕ 2023-03-02 📅 2023-03-03 ✅ 2023-03-02
- [x] ⏫ New Aspect: [Game Development](Game%20Development.md) ➕ 2023-03-03 📅 2023-03-03 ✅ 2023-03-03
