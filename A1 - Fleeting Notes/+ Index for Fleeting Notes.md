---
up: 
tags:
  - x/index
---
# Index for Fleeting Notes

``` dataview
TABLE WITHOUT ID
	file.link as "Title",
	dateformat(date, "MM/dd/yyyy" ) as "Date",
	join(file.etags) as "Tags"
FROM #type/fleeting_note or #type/fleeting-note 
WHERE !contains(file.name, "08 - Fleeting Notes")
SORT date desc
```