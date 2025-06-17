---
up: 
tags:
  - x/index
---
List of all literature notes.
``` dataview
TABLE WITHOUT ID
	file.link as "Title",
	dateformat(date, "MM/dd/yyyy") as "Date",
	dateformat(file.mtime, "MM/dd/yyyy") as "Last Modified",
	join(filter(file.etags, (t) => t != "#type/literature-note")) as "Tags"
FROM #type/literature-note
WHERE !contains(file.name, "08 - Fleeting Notes")
SORT date desc

```
