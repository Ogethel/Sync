---
tags: [[art, tracking]]
---
# Welcome to the Inktober Tracker
---
```dataview
TABLE  without id file.link as "Source", "<progress value='" + (length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text)) * 100 + "' max='100'></progress>" AS Progress
FROM "Projects/Tasks/Inktober"
WHERE file.tasks
```

---
```dataview
task
from "Projects/Tasks/Inktober"
where due = date(2022-10-04)
```
---
![[2022promptlist.jpeg]]
![[CosmereInktober2022.thumb.png.8459fa57e304390a80fbdfa7ee9a2c41.png]]

---
```dataview
task
from "Projects/Tasks/Inktober"
```


