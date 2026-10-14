---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User changes the filters of their own view and saves it
  kind: actor
  actor: sales-user
  entities:
  - entity: view
    effect: changes
    facts:
    - Filters
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
---

# Edit a view

## Trigger

A Sales User refines a saved view.

## Outcome

The view keeps the new filters.
