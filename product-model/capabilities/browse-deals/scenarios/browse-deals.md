---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens Deals
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
- text: The Product lists the deals the Sales User may see
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts:
    - Organization
    - Deal value
    - Status
    - Primary email
    - Primary mobile no
    - Assigned to
    - SLA status
    - Expected closure date
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
---

# Browse deals

## Trigger

A Sales User opens Deals from the sidebar.

## Outcome

The Sales User sees the deals they own or are assigned, in the default view.
