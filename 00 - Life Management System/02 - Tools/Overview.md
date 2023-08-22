---
share: true
type: "tool"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
---

#tool
# Quests
```dataviewjs

function write(message)
{
  return message + "\n";
}

function bullet(message)
{
  return "- " + write(message);
}

function header(message, size)
{
  let hashes = "";
  for(let i = 0; i < size; i++)
  {
    hashes += "#";
  }
  return hashes + " " + write(message);
}


let result = "";
let pages = dv.pages()
  .where(page => page["type"] == "quest");

for(let page of pages)
{
  result+= bullet(page.file.link);
}
dv.el("div", result)
```

#tool