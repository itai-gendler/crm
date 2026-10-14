---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets a task on the deal''s Tasks tab to Canceled'
  kind: actor
  actor: sales-user
  entities:
  - entity: task
    effect: changes
    from: Backlog
    to: Canceled
    facts: []
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Cancel a task

## Trigger

A follow-up is no longer needed.

## Outcome

The task is Canceled and stays on the deal.
