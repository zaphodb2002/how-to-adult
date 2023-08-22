
---
share: true
type: "aspect"
created: NaN 
modified: NaN
---
#🛌
# Things to Do
```dataviewjs
let tasks = dv.current().file.tasks
		.where(task => task.status == ' ');
		//.where(task => task.text.includes(dv.current().file.name));
console.log(dv.current().file.name)
let count = 0;

for(let task of tasks){
	let result = task.text.split("🍅")[1];
	if(result == undefined){
		continue;
	}
	count += parseInt(result.substring(0,2).trim());
	//console.log(result);
}

dv.paragraph("🍅" + count + " = ⏱" + ((count * 5)/60.0));
```





## Shopping







# Summary
campaign:: [01 - Subsistence 💗](../01%20-%20Subsistence%20%F0%9F%92%97.md)

# Routines
```dataviewjs
let campaignFolder = dv.current().file.folder;
let pages = await dv.pages('"'+campaignFolder+'"')
		.where(page => page.file.tags.includes('#routine')).file.link

dv.list(pages)
```

# Quests

# Things I've Done
```dataviewjs
let tasks = dv.pages('"' +dv.current().file.folder+'"').file.tasks
		.where(task => task.status == 'x');
console.log(tasks);
let count = 0;

for(let task of tasks){
	let result = task.text.split("🍅")[1];
	if(result == undefined){
		continue;
	}
	count += parseInt(result.substring(0,2).trim());
	//console.log(result);
}

dv.paragraph("🍅" + count + " = ⏱" + ((count * 5)/60.0));
```

## Shopping
 - [x] Buy more CPAP face socks #🛌 #shopping 🍅1 🥄1 🆙+2 ⏫ ➕ 2023-07-24 🛫 2023-07-24 ✅ 2023-07-31
- [x] Buy more fitted sheets #🛌 #shopping 🥄1 🆙+1 ⏫ ➕ 2023-07-24 🛫 2023-07-24 ✅ 2023-07-28


## Unsorted








