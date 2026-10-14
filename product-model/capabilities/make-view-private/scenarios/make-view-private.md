---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Manager chooses Make Private on a public view
  kind: actor
  actor: manager
  entities:
  - entity: view
    effect: changes
    facts:
    - Public
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
---

# Make a view private

## Trigger

A Manager withdraws a shared view.

## Outcome

Only the Manager sees the view now.
