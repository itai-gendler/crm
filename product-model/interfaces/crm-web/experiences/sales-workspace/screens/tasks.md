---
entities:
- entity: task
  shows:
  - Title
  - Priority
  - Due date
  - Assigned to
  collects:
  - Title
  - Priority
  - Assigned to
entryPoints:
- crm-web: /crm/tasks
---

# Tasks

Every task the person may see, as a list or a board by status, in the chosen view.
