---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User removes a colleague from the lead''s assignees'
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
- text: The Product clears the Lead owner and tells the colleague their assignment was removed
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

# Remove an assignee from a lead

## Trigger

A Sales User removes an assignee from a lead.

## Outcome

The colleague is no longer assigned, the lead has no owner, and the colleague is notified.

## Edge cases

- Removing one of several assignees also clears the owner
