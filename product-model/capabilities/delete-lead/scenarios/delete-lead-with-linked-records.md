---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Delete on a lead that has notes and tasks
  kind: actor
  actor: sales-user
  entities:
  - entity: note
    effect: reads
    facts:
    - Title
  - entity: task
    effect: reads
    facts:
    - Title
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Sales User chooses Delete All for the linked items, then deletes the lead'
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: removes
    from: Ongoing
  - entity: note
    effect: removes
    with: lead
  - entity: task
    effect: removes
    from: Backlog
    with: lead
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Delete a lead and its linked notes and tasks

## Trigger

A Sales User deletes a lead whose notes and tasks should go too.

## Outcome

The lead and its linked notes and tasks are gone.

## Edge cases

- Unlink All keeps the linked notes, tasks and call logs, no longer linked to anything
- Linked items the person may not change are left as they are
