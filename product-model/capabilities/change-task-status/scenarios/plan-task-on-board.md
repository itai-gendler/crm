---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User drags a task from Backlog to Todo on the tasks board
  kind: actor
  actor: sales-user
  entities:
  - entity: task
    effect: changes
    from: Backlog
    to: Todo
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::tasks'
---

# Plan a task on the board

## Trigger

A Sales User plans their week on the tasks board.

## Outcome

The task is Todo.
