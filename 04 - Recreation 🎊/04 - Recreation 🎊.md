

---
share: true
type: "aspect"
created: NaN 
modified: NaNNaN 
modified: NaN
---

# Things to Do

# Summary
campaign:: [00 - Life Management System](../00%20-%20Life%20Management%20System/00%20-%20Life%20Management%20System.md)

# Aspects
```dataviewjs
let folder = dv.current().file.folder;
let pages = await dv.pages('"'+folder+'"')
		.where(page => page.file.frontmatter['type'] == 'aspect').file.link

dv.list(pages)
```

# Things I've Done
```dataviewjs
let tasks = dv.pages('"' +dv.current().file.name+'"').file.tasks
		.where(task => task.status == 'x');
//console.log(tasks);
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