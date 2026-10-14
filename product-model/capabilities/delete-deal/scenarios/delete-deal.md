---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Delete on a deal and unlinks its linked items
  kind: actor
  actor: sales-user
  entities:
  - entity: note
    effect: changes
    facts:
    - Linked to
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Sales User confirms deleting the deal
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: removes
    from: Lost
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Product returns the Sales User to Deals
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
---

# Delete a deal

## Trigger

A Sales User deletes a deal they own.

## Outcome

The deal is gone; its notes stay, linked to nothing.
