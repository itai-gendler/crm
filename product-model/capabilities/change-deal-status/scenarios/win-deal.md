---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets the deal''s status to Won'
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    from: Ongoing
    to: Won
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Product records today as the closed date
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    facts:
    - Closed date
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Win a deal

## Trigger

A Sales User closes a deal as won.

## Outcome

The deal is Won with today's closed date.
