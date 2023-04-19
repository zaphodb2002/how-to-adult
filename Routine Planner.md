---
share: true
type: "tool"
created: NaN 
modified: NaN
---

```dataviewjs
let result = "";
let pages = dv.pages("#routine");

for(let page of pages)
{
	result += '# ' + page.file.link + '\n';
	let headers = page.file;
	console.log(page);
}

dv.paragraph(result);
```

#tool