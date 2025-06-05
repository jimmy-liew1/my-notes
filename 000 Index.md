## MOCs
Below is/are all map-of-content (MOC) in this vault.
```dataview
TABLE join(rows.file.link, "<br/>") as MOCs
FROM "B1 - MOCs"
WHERE contains(file.folder, this.file.folder) AND !contains(file.name, "index")
GROUP BY upper(file.name[0]) AS "Index"
SORT file.name ASC
FLATTEN file.link AS "Files"

```


## Notes
Below is/are all notes in this vault.
```dataview
TABLE join(rows.file.link, "<br/>") as Notes
FROM "content"
WHERE contains(file.folder, this.file.folder) AND !contains(file.name, "index")
GROUP BY upper(file.name[0]) AS "Index"
SORT file.name ASC
FLATTEN file.link AS "Files"

```