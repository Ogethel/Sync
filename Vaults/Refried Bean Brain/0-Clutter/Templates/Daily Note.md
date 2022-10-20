---
tags: [DailyNote, <% tp.date.now("MMMM") %>, <% moment().format("YYYY") %>-W<% moment().add(1, "week").format("WW") %>]
category:
status:
---

## Daily Note - <% tp.date.now("dddd Do MMMM YYYY") %>

---
[[<%tp.date.now("YYYY-MM-DD", -1)%>]]|[[<%tp.date.now("YYYY-MM-DD", 1)%>]]

---

### Notes for the Day:


### Due Today:
```dataview
task
from "Projects/Tasks"
where due = date(<%tp.date.now("YYYY-MM-DD")%>)
```

### Weekly Task Inbox
```dataview
task
from "Projects/Tasks"
where due > date(<%tp.date.now("YYYY-MM-DD")%>) and due < date(<%tp.date.now("YYYY-MM-DD", 7)%>)
sort default(due, "") ASC
```

### Schedule
```dataview
task
from "Day Planners/Day Planner-<% tp.date.now("YYYYMMDD") %>"

```
---
[[<% tp.date.now("YYYY-MM-DD") %>]] | [[<% tp.date.now("YYYY-MM") %>]] | [[<% moment().format("YYYY") %>-W<% moment().add(1, "week").format("WW") %>]]

---

Note Creation Date: <% tp.file.creation_date () %>
Note Modification Date: <% tp.file.last_modified_date ("dddd Do MMMM YYYY HH:mm:ss") %> 

--- 
<% tp.web.daily_quote() %>