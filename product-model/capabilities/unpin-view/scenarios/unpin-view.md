---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Unpin View on a pinned view
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

# Unpin a view

## Trigger

A Sales User tidies the sidebar.

## Outcome

The view is no longer in the sidebar.
