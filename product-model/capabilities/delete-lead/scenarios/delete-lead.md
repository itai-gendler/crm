---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Delete on a lead with nothing linked and confirms
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: removes
    from: Open
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: The Product returns the Sales User to Leads
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
---

# Delete a lead

## Trigger

A Sales User deletes a lead they own.

## Outcome

The lead is gone.
