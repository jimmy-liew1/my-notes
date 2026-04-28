---
up:
tags:
  - x/index
---
List of all notes in content folder (aka. published notes).
``` dataview
TABLE WITHOUT ID
	file.link as "Title",
	dateformat(date, "MM/dd/yyyy") as "Date",
	dateformat(file.mtime, "MM/dd/yyyy") as "Last Modified",
	status as "Status",
	split(file.folder, "/")[length(split(file.folder, "/")) - 1] AS "Folder",
	join(filter(file.etags, (t) => t != "#type/moc")) as "Tags",	
	length(file.outlinks) AS "Outlink",
	length(file.inlinks) AS "Backlink"
FROM "content"
WHERE !contains(file.name, this.file.name)
SORT file.mtime desc

```
