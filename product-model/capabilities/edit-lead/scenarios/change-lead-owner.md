---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User sets another salesperson as Lead owner
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Lead owner
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: The Product assigns the lead to the new owner and shares it with them
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Assigned to
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Change a lead's owner

## Trigger

A Sales User hands a lead to a colleague by changing its owner.

## Outcome

The new owner is the lead's owner and an assignee, and is notified of the assignment.
