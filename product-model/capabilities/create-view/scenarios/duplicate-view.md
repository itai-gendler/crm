---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Duplicate on a view of Leads and names the copy
  kind: actor
  actor: sales-user
  entities:
  - entity: view
    as: original
    effect: reads
    facts:
    - Label
    - Filters
  - entity: view
    as: copy
    effect: creates
    facts:
    - Label
    - View type
    - List
    - Filters
    - Sort
    - Columns
    - Kanban column
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
---

# Duplicate a view

## Trigger

A Sales User starts a view from an existing one.

## Outcome

A private copy with the new name exists.
