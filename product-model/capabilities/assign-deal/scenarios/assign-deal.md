---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User adds a colleague to the deal''s assignees'
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
- text: The Product makes the colleague the Deal owner and notifies them
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

# Assign a deal

## Trigger

A Sales User assigns a deal to a colleague.

## Outcome

The colleague is assigned, owns the deal and has an Assignment notification.
