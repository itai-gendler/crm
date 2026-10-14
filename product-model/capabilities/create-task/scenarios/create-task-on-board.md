---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User adds a task in the In Progress column of the tasks board
  kind: actor
  actor: sales-user
  entities:
  - entity: task
    effect: creates
    to: In Progress
    facts:
    - Title
    - Priority
  contexts:
    main:
      place: 'crm-web::sales-workspace::tasks'
---

# Create a task in a board column

## Trigger

A Sales User creates a task straight into a status on the board.

## Outcome

The task is In Progress.
