---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens a call log and chooses Add Note
  kind: actor
  actor: sales-user
  entities:
  - entity: call-log
    effect: reads
    facts:
    - Linked to
  - entity: note
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::call-logs'
- text: The Sales User writes the note and saves it
  kind: actor
  actor: sales-user
  entities:
  - entity: note
    effect: creates
    facts:
    - Title
    - Content
    - Linked to
  - entity: call-log
    effect: changes
    facts:
    - Call notes
  contexts:
    main:
      place: 'crm-web::sales-workspace::call-logs'
---

# Add a note about a call

## Trigger

A Sales User writes up a call.

## Outcome

The note is on the call log and on the call's lead or deal.
