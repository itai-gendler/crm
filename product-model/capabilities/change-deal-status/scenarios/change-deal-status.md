---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets the deal''s status to Proposal/Quotation'
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    from: Open
    to: Ongoing
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Product logs how long the deal spent in its previous status
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Move a deal to the next stage

## Trigger

A Sales User advances a deal from its status menu.

## Outcome

The deal is in Proposal/Quotation.

## Edge cases

- A deal whose probability is empty takes the new status's probability
