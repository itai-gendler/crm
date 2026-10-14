---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User changes the lead''s job title, territory and products on its page'
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Job title
    - Territory
    - Products
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product recalculates the products'' net total and saves the lead'
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Net total
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Edit a lead's details

## Trigger

A Sales User edits fields on a lead they own.

## Outcome

The lead holds the new values and its Activity tab shows the change.
