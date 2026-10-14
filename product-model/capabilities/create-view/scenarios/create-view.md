---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User filters Deals, picks columns and chooses Create View with a name and icon'
  kind: actor
  actor: sales-user
  entities:
  - entity: view
    effect: creates
    facts:
    - Label
    - Icon
    - View type
    - List
    - Filters
    - Sort
    - Columns
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
---

# Save a view

## Trigger

A Sales User wants to come back to a filtered list.

## Outcome

The view is saved, private to the Sales User, and opens.
