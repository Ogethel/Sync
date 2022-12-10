---
tags: [Jewelry, Dashboard]
---

# Active Jewelry Projects & Progress
 ---

## Paxtons Ring
```dataview
TABLE  without id "<progress value='" + (length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text)) * 100 + "' max='100'></progress>" AS Progress
FROM "Projects/Tasks/Backlogs/BL_Jewelry"
WHERE file.tasks & meta([[BL_Jewelry#Paxtons Ring]]).subpath
```
#### Manufacture Full Line of Pendants
```dataview
task
from "Projects/Tasks/Backlogs/BL_Jewelry"
sort default(due, "") ASC
where meta(section).subpath = "Paxtons Ring"
```

## Skull Arrowhead
```dataview
task
from "Projects/Tasks/Backlogs/BL_Jewelry"
sort default(due, "") ASC
where meta(section).subpath = "Skull Arrowhead"
```

## Christmas Pendant Lineup
```dataview
task
from "Projects/Tasks/Backlogs/BL_Jewelry"
sort default(due, "") ASC
where meta(section).subpath = "Christmas"
```
