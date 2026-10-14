---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Unpin on a pinned note of the lead
  kind: actor
  actor: sales-user
  entities:
  - entity: note
    effect: changes
    facts:
    - Pinned
    - Pinned by
    - Pinned on
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Unpin a note

## Trigger

A Sales User no longer needs a note on top.

## Outcome

The note returns to its place among the notes.
