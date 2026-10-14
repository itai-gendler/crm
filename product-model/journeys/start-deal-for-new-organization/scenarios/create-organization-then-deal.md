---
kind: primary
result: achieved
routes:
  main: Sales workspace
steps:
- text: The Sales User creates the organization
  kind: actor
  actor: sales-user
  entities:
  - entity: organization
    effect: creates
    facts:
    - Organization name
    - Website
    - Industry
    - No. of employees
    - Annual revenue
    - Currency
  contexts:
    main:
      place: 'crm-web::sales-workspace::organizations'
  capability: create-organization
- text: 'The Product opens the new organization''s page'
  kind: product
  actor: sales-user
  entities:
  - entity: organization
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::organization'
  capability: create-organization
- text: The Sales User chooses New Deal there and creates the deal
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: creates
    to: Open
    facts:
    - Organization
    - Status
    - Deal owner
    - Deal value
    - Expected deal value
    - Expected closure date
  contexts:
    main:
      place: 'crm-web::sales-workspace::organization'
  capability: create-deal
---

# Create an organization, then a deal with it

## Trigger

A Sales User creates an organization on Organizations.

## Outcome

The organization has a new deal.
