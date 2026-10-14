---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User drags a deal card from Negotiation to Ready to Close on the deals board
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    from: Ongoing
    to: Ongoing
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
---

# Drag a deal to another column

## Trigger

A Sales User works the pipeline on the kanban board.

## Outcome

The deal is in Ready to Close.
