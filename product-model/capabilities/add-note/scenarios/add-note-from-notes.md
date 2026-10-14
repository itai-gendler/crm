---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User creates a note with a title and content on Notes
  kind: actor
  actor: sales-user
  entities:
  - entity: note
    effect: creates
    facts:
    - Title
    - Content
  contexts:
    main:
      place: 'crm-web::sales-workspace::notes'
---

# Add a note from Notes

## Trigger

A Sales User writes a note that belongs to no record.

## Outcome

The note shows in Notes.
