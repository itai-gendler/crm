---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User writes a comment on the deal mentioning a colleague and sends it
  kind: actor
  actor: sales-user
  entities:
  - entity: comment
    effect: creates
    facts:
    - Content
    - Author
    - Mentions
    - Linked to
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Product notifies the mentioned colleague
  kind: product
  actor: sales-user
  entities:
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

# Comment with a mention

## Trigger

A Sales User wants a colleague's eyes on a deal.

## Outcome

The comment shows on the deal and the colleague has a Mention notification that opens it.

## Edge cases

- Mentioning oneself sends no notification
