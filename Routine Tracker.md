---
share: true
type: "tool"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
---

#tool
## Morning (0600 - 1200)
```tasks
limit 1
path includes Daily Notes
due after yesterday
tags include #morning
not done
short mode
```
## Afternoon (1200 - 1800)
```tasks
limit 1
path includes Daily Notes
due after yesterday
tags include #afternoon
not done
short mode
```
## Evening (1800- 2400)
```tasks
limit 1
path includes Daily Notes
due after yesterday
tags include #evening
not done
short mode
```
#tool