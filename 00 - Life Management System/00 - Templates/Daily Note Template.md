---
created: <% tp.file.creation_date() %> 
modified: <% tp.file.last_modified_date() %>
---
# <%moment(tp.file.title, 'YYYY-MM-DD').format("dddd, MMMM DD, YYYY")%>
<<[<% tp.date.now("YYYY-MM-DD", -1) %>](<% tp.date.now("YYYY-MM-DD", -1) %>.md) || [<% tp.date.now("YYYY-MM-DD", 1) %>](<% tp.date.now("YYYY-MM-DD", 1) %>.md) >>

---

- 