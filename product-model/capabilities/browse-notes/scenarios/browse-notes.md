---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens Notes
  kind: actor
  actor: sales-user
  entities:
  - entity: note
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::notes'
- text: 'The Product lists notes with their title, content and the lead or deal they belong to'
  kind: product
  actor: sales-user
  entities:
  - entity: note
    effect: reads
    facts:
    - Title
    - Content
    - Linked to
  - entity: lead
    effect: reads
    facts: []
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::notes'
---

# Browse notes

## Trigger

A Sales User opens Notes from the sidebar.

## Outcome

The Sales User sees the notes and can open one.
