---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User edits a note on the deal and mentions another colleague
  kind: actor
  actor: sales-user
  entities:
  - entity: note
    effect: changes
    facts:
    - Content
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Product notifies only the newly mentioned colleague
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
      place: 'crm-web::sales-workspace::deal'
---

# Edit a note

## Trigger

A Sales User updates a note.

## Outcome

The note holds the new content; people mentioned before are not notified again.
