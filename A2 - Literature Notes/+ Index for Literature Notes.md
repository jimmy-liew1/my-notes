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
	join(filter(file.etags, (t) => t != "#type/literature-note")) as "Tags",
	length(file.outlinks) AS "Outlink",
	length(file.inlinks) AS "Backlink"
FROM #type/literature-note
WHERE !contains(file.name, this.file.name)
SORT date desc

```
