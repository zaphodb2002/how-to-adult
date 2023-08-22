---
share: true
alias: "Subsistence"
type: "campaign"
created: NaN 
modified: NaN
---

# Things to Sort


# Summary

# Aspects
```dataviewjs
let folder = dv.current().file.folder;
let pages = await dv.pages('"'+folder+'"')
		.where(page => page.file.frontmatter['type'] == 'aspect').file.link

dv.list(pages)
```



# Things I've Done
```dataviewjs
let tasks = dv.pages('"' +dv.current().file.folder+'"').file.tasks
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

```dataviewjs
let tasks = dv.pages('"' +dv.current().file.folder+'"').file.tasks
		.where(task => task.status == 'x');
//console.log(tasks);
let count = 0;

for(let task of tasks){
	let result = task.text.split("🆙")[1];
	if(result == undefined){
		continue;
	}
	var xpStr = result.substring(0,2).trim().trim().replace("+",'')
	var xp = parseInt(xpStr);
	console.log(xp + " - " + result + ":" + xpStr)
	count += xp;
	
}

dv.paragraph("🆙" + count);
``