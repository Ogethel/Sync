---
tags: [DailyNote, <% tp.date.now("MMMM") %>, <% moment().format("YYYY") %>-W<% moment().add(1, "week").format("WW") %>]
category:
status:
---

## Daily Note - <% tp.date.now("dddd Do MMMM YYYY") %>

---
[[<%tp.date.now("YYYY-MM-DD", -1)%>]]|[[<%tp.date.now("YYYY-MM-DD", 1)%>]]

---

### Questions;
Service done in love of God and our fellow man is one of the highest forms of worship and the medium through which God has ordained some lessons must be learned.  In light of this realization, ponder the following:
- In my obligations today, how may I increase my love for my fellow men and how may I better minister and serve them?
- Have I consumed or am I consuming things upon my own lust as consequence of my pride?
- I have worldly obligations here.  
	- Am I at my computer, phone, book, or chore to improve, perform, and learn efficiently so as to meet and exceed those obligations?  
	- If the weakness of my flesh requires I take a break, am I doing so in a wise way?

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