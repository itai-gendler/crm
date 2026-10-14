---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User chooses Reply All on an email in the deal''s timeline'
  kind: actor
  actor: sales-user
  entities:
  - entity: email-message
    effect: reads
    facts:
    - Subject
    - From
    - To
    - CC
    - Content
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Sales User writes the answer and sends it
  kind: actor
  actor: sales-user
  entities:
  - entity: email-message
    effect: creates
    facts:
    - Subject
    - Content
    - From
    - To
    - CC
    - Direction
    - Linked to
    - Sent at
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Reply to a prospect's email

## Trigger

A prospect has written on a deal and a Sales User answers.

## Outcome

The reply is sent to the sender and every recipient, and kept on the deal.
