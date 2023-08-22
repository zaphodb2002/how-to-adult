---
share: true
type: "tool"
created: NaN 
modified: NaN
---
# Active
```dataviewjs
let result = "";
let pages = dv.pages("#routine")
.where(page => page["status"] == "active");

for(let page of pages)
{
	result += '- ' + page.file.link + '\n';
	let headers = page.file;
	//console.log(page);
}

dv.paragraph(result);
```

# Available
```dataviewjs
let result = "";
let pages = dv.pages("#routine")
.where(page => page["status"] != "active");

for(let page of pages)
{
	result += '- ' + page.file.link + '\n';
	let headers = page.file;
	//console.log(page);
}

dv.paragraph(result);
```

#tool