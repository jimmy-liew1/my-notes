---
up: 
tags:
  - x/index
---
List of all fleeting notes.
``` dataview
TABLE WITHOUT ID
	file.link as "Title",
	dateformat(date, "MM/dd/yyyy") as "Date",
	dateformat(file.mtime, "MM/dd/yyyy") as "Last Modified",
	join(filter(file.etags, (t) => t != "#type/fleeting-note")) as "Tags"
FROM #type/fleeting-note
WHERE !contains(file.name, "08 - Fleeting Notes")
SORT date desc

```
