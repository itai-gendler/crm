---
kind: validation
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses the Junk status and dismisses the lost reason
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product refuses to save the status: a reason for losing the lead is required'
  kind: condition
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Lost reason
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Mark a lead as lost without a reason

## Trigger

A Sales User moves a lead to a Lost status without giving a reason.

## Outcome

The lead keeps its previous status.

## Edge cases

- Lost reason Other without lost notes is refused the same way
