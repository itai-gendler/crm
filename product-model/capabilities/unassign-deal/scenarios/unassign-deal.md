---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User removes a colleague from the deal''s assignees'
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    facts:
    - Assigned to
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Product clears the Deal owner and tells the colleague their assignment was removed
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    facts:
    - Deal owner
  - entity: notification
    effect: creates
    facts:
    - Type
    - From
    - Message
    - Read
    - Linked to
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Remove an assignee from a deal

## Trigger

A Sales User removes an assignee from a deal.

## Outcome

The colleague is no longer assigned and the deal has no owner.
