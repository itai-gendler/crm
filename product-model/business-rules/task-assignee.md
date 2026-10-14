---
appliesTo:
- type: entity
  id: task
  facts:
  - Assigned to
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_task/crm_task.py
---

# A task is assigned to one person at a time

Changing a task's assignee removes the previous person's assignment.
