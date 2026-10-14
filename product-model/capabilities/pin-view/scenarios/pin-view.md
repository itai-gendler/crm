---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Pin View on their own view
  kind: actor
  actor: sales-user
  entities:
  - entity: view
    effect: changes
    facts:
    - Pinned
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
---

# Pin a view

## Trigger

A Sales User wants a view one click away.

## Outcome

The view shows under Pinned Views in the sidebar.
