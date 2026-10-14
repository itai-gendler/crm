---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Delete on a task in Tasks and confirms
  kind: actor
  actor: sales-user
  entities:
  - entity: task
    effect: removes
    from: Canceled
  contexts:
    main:
      place: 'crm-web::sales-workspace::tasks'
---

# Delete a task

## Trigger

A Sales User removes a task no longer needed.

## Outcome

The task is gone.
