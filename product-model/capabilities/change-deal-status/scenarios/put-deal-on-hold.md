---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets the deal''s status to Stalled, a configured status of the On Hold type'
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    from: Ongoing
    to: On Hold
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Put a deal on hold

## Trigger

A deal stalls.

## Outcome

The deal is on hold.
