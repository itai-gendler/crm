---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Delete Attachment on a file of the deal and confirms
  kind: actor
  actor: sales-user
  entities:
  - entity: attachment
    effect: removes
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Delete an attachment

## Trigger

A Sales User removes an outdated file.

## Outcome

The file is gone from the deal.
