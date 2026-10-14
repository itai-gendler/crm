---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Mark all as read
  kind: actor
  actor: sales-user
  entities:
  - entity: notification
    effect: changes
    facts:
    - Read
  contexts:
    main:
      place: 'crm-web::sales-workspace::notifications'
---

# Mark all as read

## Trigger

A Sales User clears their unread notifications.

## Outcome

No unread notifications remain.
