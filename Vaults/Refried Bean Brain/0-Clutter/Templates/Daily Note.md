---
tags: [DailyNote, <% tp.date.now("MMMM", 0, tp.file.title, "YYYY-MM-DD") %>, <% tp.date.now("YYYY", 0, tp.file.title, "YYYY-MM-DD") %>-W<% tp.date.now("WW", 7, tp.file.title, "YYYY-MM-DD") %>]
category:
status:
---

# Daily Note - <% tp.date.now("dddd Do MMMM YYYY", 0, tp.file.title, "YYYY-MM-DD") %>

---
[[<%tp.date.now("YYYY-MM-DD", -1, tp.file.title, "YYYY-MM-DD")%>]]|[[<%tp.date.now("YYYY-MM-DD", 1, tp.file.title, "YYYY-MM-DD")%>]]

---

## Notes for the Day:
### Active Projects
#### Rookies
[[Moto the Bruiser]]
#### Website
#### Skull Arrowhead
[[Skull-Arrowhead]]
#### Humble Bundles

### Notes
#### Day Outline + Goals

#### Journal Entry

## Backlog
[[D-Past Due & No Date]]

## Due Today:
```dataview
task
from "Projects/Tasks"
where due = date(<%tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYY-MM-DD")%>)
GROUP BY header
```

## Weekly Task Inbox
```dataview
task
from "Projects/Tasks"
where due > date(<%tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYY-MM-DD")%>) and due < date(<%tp.date.now("YYYY-MM-DD", 7, tp.file.title, "YYYY-MM-DD")%>)
sort default(due, "") ASC
GROUP BY header
```

## Schedule
```dataview
task
from "Day Planners/Day Planner-<% tp.date.now("YYYYMMDD", 0, tp.file.title, "YYYY-MM-DD") %>"

```
---
[[<% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYY-MM-DD") %>]] | [[<% tp.date.now("YYYY-MM", 0, tp.file.title, "YYYY-MM-DD") %>]] | [[<% tp.date.now("YYYY", 0, tp.file.title, "YYYY-MM-DD") %>-W<% tp.date.now("WW", 7, tp.file.title, "YYYY-MM-DD") %>]]

---

Note Creation Date: <% tp.file.creation_date () %>
Note Modification Date: <% tp.file.last_modified_date ("dddd Do MMMM YYYY HH:mm:ss") %> 

---
### Questions to Ponder
	Service done in love of God and our fellow man is one of the highest forms of worship and the medium through which God has ordained some lessons must be learned.  In light of this realization, ponder the following:
	- In my obligations today, how may I increase my love for my fellow men and how may I better minister and serve them?
	- Have I consumed or am I consuming things upon my own lust as consequence of my pride?
	- I have worldly obligations here.  
		- Am I at my computer, phone, book, or chore to improve, perform, and learn efficiently so as to meet and exceed those obligations?  
		- If the weakness of my flesh requires I take a break, am I doing so in a wise way?

--- 
<% tp.web.daily_quote() %>