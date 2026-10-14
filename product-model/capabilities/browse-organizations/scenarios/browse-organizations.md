---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens Organizations
  kind: actor
  actor: sales-user
  entities:
  - entity: organization
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::organizations'
- text: 'The Product lists organizations with their website, industry and annual revenue'
  kind: product
  actor: sales-user
  entities:
  - entity: organization
    effect: reads
    facts:
    - Organization name
    - Website
    - Industry
    - Annual revenue
  contexts:
    main:
      place: 'crm-web::sales-workspace::organizations'
---

# Browse organizations

## Trigger

A Sales User opens Organizations from the sidebar.

## Outcome

The Sales User sees the organizations.
