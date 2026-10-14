---
kind: validation
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets the deal''s status to Lost and closes the lost reason dialog'
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: 'The Product refuses: a reason for losing the deal is required'
  kind: condition
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts:
    - Lost reason
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Lose a deal without a reason

## Trigger

A Sales User loses a deal without saying why.

## Outcome

The deal keeps its previous status.

## Edge cases

- Lost reason Other without lost notes is refused the same way
