---
type: dashboard
hub: home
status: active
date: 2026-06-30
---

# Dashboard

## Active Projects (plain-text for Claude)

<!-- This section is read by Claude. Update manually or via "save progress". -->

| Project | Status | Deadline | Next Step |
|---------|--------|----------|-----------|
| werkstudent | active | ASAP | send applications |
| studium (M.Sc. BUA) | active | exam session | track Prüfungen |
| personal-kb | active | ongoing | vault setup |

## Active Tasks (Obsidian Dataview)

```dataview
TABLE project, due, file.link AS "Task"
FROM "00 Home"
WHERE type = "task" AND status = "pending"
SORT due ASC
```

## Active Projects (Obsidian Dataview)

```dataview
TABLE status, file.mtime AS "Updated", file.link AS "Project"
FROM "02 Projects"
WHERE type = "status"
SORT file.mtime DESC
LIMIT 10
```

## Recent Decisions

```dataview
TABLE project, topic, file.link AS "Decision"
FROM "02 Projects" OR "03 Knowledge"
WHERE type = "decision"
SORT date DESC
LIMIT 5
```

## Recent Ideas

```dataview
TABLE date, file.link AS "Idea"
FROM "06 Ideas/fleeting"
WHERE type = "idea"
SORT date DESC
LIMIT 5
```

## Documents Expiring Soon

```dataview
TABLE category, valid_until, file.link AS "Document"
FROM "05 Documents"
WHERE type = "document" AND status = "active"
SORT valid_until ASC
LIMIT 5
```

## Recent Knowledge

```dataview
TABLE topic, file.link AS "Note"
FROM "03 Knowledge"
WHERE type = "knowledge"
SORT date DESC
LIMIT 5
```
