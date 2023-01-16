---
tags: [DailyPlanner, <% tp.date.now("MMMM", 0, tp.file.title, "YYYYMMDD") %>, <% tp.date.now("YYYY", 0, tp.file.title, "YYYYMMDD") %>-W<% tp.date.now("WW", 7, tp.file.title, "YYYYMMDD") %>]
category:
status:
---

## Daily Planner - <% tp.date.now("dddd Do MMMM YYYY") %>

---
[[<% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYYMMDD") %>]] | [[<% tp.date.now("YYYY-MM", 0, tp.file.title, "YYYYMMDD") %>]] | [[<% tp.date.now("YYYY", 0, tp.file.title, "YYYYMMDD") %>-W<% tp.date.now("WW", 7, tp.file.title, "YYYYMMDD") %>]]

---
### Schedule
- [ ] 07:00 Wake Up
- [ ] 07:15 Read Scriptures in Bed
- [ ] 08:30 Work out (A, L, C)
- [ ] 08:30 Feed Babies
- [ ] 09:00 Walk Worf
- [ ] 09:30 Read Scriptures
- [ ] 10:00 Game Dev
- [ ] 11:00 Pendant
- [ ] 21:30 Record Journal
- [ ] 22:00 END

---
[[Day Planner-<% tp.date.now("YYYYMMDD", -1, tp.file.title, "YYYYMMDD") %>]]|[[Day Planner-<% tp.date.now("YYYYMMDD", 1, tp.file.title, "YYYYMMDD") %>]]
[[Day Planner-<% tp.date.now("YYYYMMDD", 0, tp.file.title, "YYYYMMDD") %>]]

---

Note Creation Date: <% tp.file.creation_date () %>
Note Modification Date: <% tp.file.last_modified_date ("dddd Do MMMM YYYY HH:mm:ss") %> 

--- 
<% tp.web.daily_quote() %>