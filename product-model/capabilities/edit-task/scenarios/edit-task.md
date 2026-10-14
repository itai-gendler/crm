---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens a task in Tasks and assigns it to another colleague
  kind: actor
  actor: sales-user
  entities:
  - entity: task
    effect: changes
    facts:
    - Assigned to
  contexts:
    main:
      place: 'crm-web::sales-workspace::tasks'
- text: 'The Product removes the previous person''s assignment and notifies both'
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
  contexts:
    main:
      place: 'crm-web::sales-workspace::tasks'
---

# Reassign a task

## Trigger

A Sales User hands a task over.

## Outcome

The task is assigned to the new colleague only.
