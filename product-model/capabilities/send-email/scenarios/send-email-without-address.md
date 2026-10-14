---
kind: validation
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Send an Email on a lead with no email address
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Email
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product refuses: Please set an email address to send emails'
  kind: condition
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Email a lead without an email address

## Trigger

A Sales User tries to email a lead whose email is empty.

## Outcome

No email box opens.
