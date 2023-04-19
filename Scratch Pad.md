---
share: true
type: "tool"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
---
###### Python
```run-python
thing = "foo"
thing2 = "bar"
thing3 = thing + thing2

print(thing3)
```


###### JavaScript
```run-javascript
function write()
{
    let thing = "foo";
    let thing2 = "bar";
    return(thing + thing2);
}

console.log(write());

```

#tool