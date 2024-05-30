Link: [[000 Index|Back to Index]]
tags:: #type/moc

----
## Key Topics
```dataview
LIST FROM ([[#]]) OR outgoing([[#]])
WHERE file.name != this.file.name and file.name != "000 Index" and !contains(file.name, "MOC") and contains(file.tags, "#topic-note")
SORT file.name ASC
```

## Topics
```dataview
LIST FROM ([[#]]) OR outgoing([[#]])
WHERE file.name != this.file.name and file.name != "000 Index" and !contains(file.name, "MOC") and !contains(file.tags, "#topic-note")
SORT file.name ASC
```
