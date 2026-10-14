---
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_task/crm_task.py
---

# Task

A to-do for someone on the sales team, on a lead or deal or on its own.

## Information kept

- **Title** — what to do
- **Description** — details
- **Priority** — Low, Medium or High
- **Start date** — when to start
- **Due date** — when it is due
- **Assigned to** — the person who should do it
- **Linked to** — the lead or deal it belongs to

## States

### Backlog

Not yet planned.

### Todo

Planned.

### In Progress

Being worked.

### Done

Finished.

### Canceled

No longer needed.
