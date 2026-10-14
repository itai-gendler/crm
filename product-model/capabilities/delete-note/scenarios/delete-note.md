---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Delete on a note in Notes and confirms
  kind: actor
  actor: sales-user
  entities:
  - entity: note
    effect: removes
  contexts:
    main:
      place: 'crm-web::sales-workspace::notes'
---

# Delete a note

## Trigger

A Sales User removes a note.

## Outcome

The note is gone.
