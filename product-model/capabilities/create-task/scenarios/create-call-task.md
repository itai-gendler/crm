---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens a call log and chooses Add Task
  kind: actor
  actor: sales-user
  entities:
  - entity: call-log
    effect: reads
    facts:
    - Linked to
  - entity: task
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::call-logs'
- text: The Sales User enters the task and saves it
  kind: actor
  actor: sales-user
  entities:
  - entity: task
    effect: creates
    to: Backlog
    facts:
    - Title
    - Priority
    - Linked to
  - entity: call-log
    effect: changes
    facts:
    - Call tasks
  contexts:
    main:
      place: 'crm-web::sales-workspace::call-logs'
---

# Create a task from a call

## Trigger

A Sales User plans a follow-up after a call.

## Outcome

The task is on the call log and on the call's lead or deal.
