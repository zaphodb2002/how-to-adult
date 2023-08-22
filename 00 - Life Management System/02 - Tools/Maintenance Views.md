---
share: true
type: "tool"
created: NaN 
modified: NaN
---
# Routines
## Routines with invalid Metadata
```dataviewjs
const pages = dv.pages()
.where(page => page["type"] == "routine")
.where(
	page => page["status"] == undefined
	 );

let result = "";
for (let page of pages)
{
	result += page.file.link + ": \n";
	result += "status: " + page["status"] + '\n\n';
	
}
dv.el("div", result);
```
# Tasks
## Tasks due but not started
```tasks
has due date
no start date
not done
path does not include Routine
```
## Tasks with no Campaign Associated Tags
```dataviewjs

const tasks = dv.pages('"01 - Subsistence 💗"').file.tasks
		.where(task => !task.tags.includes('#🛌')
					&& !task.tags.includes('#🌊')
					&& !task.tags.includes('#🍎')
					&& !task.tags.includes('#💊')
					&& !task.tags.includes('#🚿')
					&& !task.tags.includes('#💪')
					&& !task.tags.includes('#😢')
					&& !task.tags.includes('#⏰')
					&& !task.tags.includes('#🧭')
					&& !task.tags.includes('#⛈')
		)
		.where(task => task.status == ' ')
		

//console.log(tasks)

dv.taskList(tasks, true)
```
## Tasks with no tomatoes 🍅
```tasks
description does not include 🍅
description does not include +
not done
path does not include Routine
```

## Tasks with no spoons 🥄
```tasks
description does not include 🥄
description does not include +
not done
path does not include Routine
```
## Tasks with no XP 🆙
```tasks
description does not include 🆙
description does not include +
not done
path does not include Routine
```
# Notes
## Notes that Don't Exist
```dataviewjs
const pages = dv.pages()
.where(page => page.file.outlinks.length > 0);
let result = "";

for (let page of pages)
{
	
	for (let link of page.file.outlinks)
	{
		if(dv.page(link) == undefined)
			result += page.file.link + ': ' + link + '\n';
	}
}

dv.el("div", result);
```
## Notes with No Content
```dataviewjs
const pages = dv.pages().where(page => page.file.size < 50)

dv.list(pages.file.link)
```
## Notes with No Links
```dataviewjs
const pages = dv.pages()
.where(page => page.file.inlinks.length == 0)
.where(page => page.file.outlinks.length == 0);
let result = "";
for (let page of pages)
{
	result += page.file.link + '\n';
}
dv.el("div", result);
```
## Notes with Invalid Metadata
```dataviewjs
const pages = dv.pages()
.where(
	page => page["share"] == undefined
	|| page["type"] == undefined
	 )
.where(page => !page.file.path.includes("Template"));

let result = "";
for (let page of pages)
{
	result += page.file.link + ": \n";
	result += "share: " + page["share"] + '\n';
	result += "type: " + page["type"] + '\n';
	result += '\n';
	
	
}
dv.el("div", result);
```

#tool