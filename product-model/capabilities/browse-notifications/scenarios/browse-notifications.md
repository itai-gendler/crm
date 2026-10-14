---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens Notifications
  kind: actor
  actor: sales-user
  entities:
  - entity: notification
    effect: reads
    facts:
    - Type
    - From
    - Message
    - Read
    - Linked to
  contexts:
    main:
      place: 'crm-web::sales-workspace::notifications'
- text: The Sales User opens a mention
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
- text: The Product opens the lead at the mentioning comment
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts: []
  - entity: comment
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Open a notification

## Trigger

A Sales User sees an unread count.

## Outcome

The Sales User is on the lead at the comment, and the notification is read.
