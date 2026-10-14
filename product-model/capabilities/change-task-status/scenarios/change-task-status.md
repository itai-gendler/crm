---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets a task on the lead''s Tasks tab to Done'
  kind: actor
  actor: sales-user
  entities:
  - entity: task
    effect: changes
    from: In Progress
    to: Done
    facts: []
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Mark a task done

## Trigger

A Sales User finishes a follow-up.

## Outcome

The task is Done.
