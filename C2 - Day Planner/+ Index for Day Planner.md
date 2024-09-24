---
up: 
tags:
  - x/index
---

List all my open tasks:
```dataview
TASK FROM #daily-planner AND -#template
WHERE !completed AND file.name != "02 - Day Planner"
GROUP BY file.folder
```

