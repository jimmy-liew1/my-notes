---
up: "[[Cloud Computing MOC]]"
tags:
  - type/moc
---
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

## Related Notes
```dataview
LIST FROM #azure
WHERE file.name != this.file.name
  AND file.name != "000 Index"
  AND !contains(file.name, "MOC")
  AND !contains(file.tags, "#topic-note")
SORT file.name ASC
```