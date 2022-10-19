---
---

# Test Project to Use as an Example

## Project Purpose
	Synopsis 
Primary purpose for the project;
In this case the primary purpose of this project is to make an adaptable template that lets me see and test different potential workflows for making and maintaining projects inside Obsidian


```dataview
TABLE file.tasks.text, length(file.tasks.text) as Total, file.tasks.completed, filter(file.tasks.completed, (t) => t = true) as C, length(filter(file.tasks.completed, (t) => t = true)) AS Completed, (length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text)) * 100 AS BB, "<progress value='" + (length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text)) * 100 + "' max='100'></progress>" AS Progress
FROM "Projects/Tasks"
WHERE file.tasks
```

```dataview
TABLE "<progress value='" + (length(filter(file.tasks.completed, (t) => t = true)) / length(file.tasks.text)) * 100 + "' max='100'></progress>" AS Progress
FROM "Projects/Tasks/A New Test File"
WHERE file.tasks
```

```dataview
TABLE file.name AS "Source", rating AS "Raiting"
FROM #book
```