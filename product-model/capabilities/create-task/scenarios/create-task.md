---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User chooses New Task on the deal and enters a title, priority, due date and a colleague to do it'
  kind: actor
  actor: sales-user
  entities:
  - entity: task
    effect: creates
    to: Backlog
    facts:
    - Title
    - Priority
    - Due date
    - Assigned to
    - Linked to
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Product notifies the colleague of the task
  kind: product
  actor: sales-user
  entities:
  - entity: notification
    effect: creates
    facts:
    - Type
    - From
    - Message
    - Read
    - Linked to
  - entity: task
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Create a task on a deal

## Trigger

A Sales User plans a follow-up on a deal.

## Outcome

The task is in Backlog on the deal's Tasks tab and the colleague is notified.
