---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User enters the organization''s name, website, industry and size and creates it'
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
- text: 'The Product sets its exchange rate to the CRM''s currency and opens its page'
  kind: product
  actor: sales-user
  entities:
  - entity: organization
    effect: changes
    facts:
    - Exchange rate
  contexts:
    main:
      place: 'crm-web::sales-workspace::organization'
---

# Create an organization

## Trigger

A Sales User chooses Create on Organizations.

## Outcome

The Sales User is on the new organization's page.
