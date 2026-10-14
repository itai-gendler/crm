---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets the deal''s status to Lost'
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
- text: The Sales User picks the lost reason Competition
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    from: Ongoing
    to: Lost
    facts:
    - Status
    - Lost reason
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Lose a deal

## Trigger

A Sales User records a lost deal.

## Outcome

The deal is Lost with its reason.
