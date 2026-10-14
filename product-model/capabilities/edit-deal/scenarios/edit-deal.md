---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User adds products and sets the expected closure date and next step
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    facts:
    - Products
    - Expected closure date
    - Next step
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Product recalculates the net total and keeps the expected deal value in step with it
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    facts:
    - Net total
    - Expected deal value
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Edit a deal's details

## Trigger

A Sales User updates a deal they own.

## Outcome

The deal holds the new values and its activity shows the change.

## Edge cases

- Changing the currency fetches a new exchange rate to the CRM's currency
- Changing the Deal owner assigns and shares the deal with the new owner

## Decision points

### Expected deal value

Is Auto update Expected Deal Value on and does the deal already have an expected value?

- Yes → the expected deal value becomes the net total
- No → it stays as entered
