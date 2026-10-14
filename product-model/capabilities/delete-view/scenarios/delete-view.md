---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Delete on their own view and confirms
  kind: actor
  actor: sales-user
  entities:
  - entity: view
    effect: removes
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
---

# Delete a view

## Trigger

A Sales User no longer needs a view.

## Outcome

The view is gone.
