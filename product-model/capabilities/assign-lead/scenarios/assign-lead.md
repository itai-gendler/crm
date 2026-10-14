---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User adds a colleague to the lead''s assignees'
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Assigned to
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: The Product makes the colleague the Lead owner and notifies them
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Lead owner
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
      place: 'crm-web::sales-workspace::lead'
---

# Assign a lead

## Trigger

A Sales User assigns a lead they own to a colleague.

## Outcome

The colleague is assigned, owns the lead and has an Assignment notification.

## Edge cases

- Assigning oneself sends no notification
