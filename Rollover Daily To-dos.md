---
share: true
type: "knowledge"
sub-type: "tool"
created: <%+ tp.file.creation_date() %> 
modified: <%+ tp.file.last_modified_date() %>
---
#LMS 
Not in use
Replaced with [Templater](./Templater.md)

# Links


# Known Issues

1. ~~2023-03-02 - Duplicates tasks if they are also in the template for the daily note.~~
	1. Happens if you insert the template manually
	2. Order of operations issues.  [Templater](./Templater.md) applies template then tasks roll over
	3. 2023-03-08 12:43 this is resolved now, I use a task view for routines now
2. 2023-03-02 - Deletes tasks if you make the daily note
	1. basically the opposite of issue #1, applies the rollover then overwrites with the template.
	2. Resolved by doing it manually and not setting it to automatic but that causes issue #1
	4. Does not currently support in progress todos [github issue](https://github.com/lumoe/obsidian-rollover-daily-todos/issues/87)

