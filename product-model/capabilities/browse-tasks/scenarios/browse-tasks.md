---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens Tasks
  kind: actor
  actor: sales-user
  entities:
  - entity: task
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::tasks'
- text: 'The Product lists tasks with their priority, due date and assignee'
  kind: product
  actor: sales-user
  entities:
  - entity: task
    effect: reads
    facts:
    - Title
    - Priority
    - Due date
    - Assigned to
  contexts:
    main:
      place: 'crm-web::sales-workspace::tasks'
---

# Browse tasks

## Trigger

A Sales User opens Tasks from the sidebar.

## Outcome

The Sales User sees the tasks.
