---
share: true
alias: "CHANGE THIS TO THE CAMPAIGN NAME"
type: "campaign"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
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