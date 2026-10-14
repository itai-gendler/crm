---
kind: validation
routes:
  main: Sales workspace
steps:
- text: The Sales User opens the WhatsApp tab of a lead with no mobile number
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Mobile no.
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product offers no message box: Add a mobile number to send WhatsApp messages'
  kind: condition
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts: []
  - entity: whatsapp-message
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Message a lead without a mobile number

## Trigger

A Sales User wants to message a lead whose mobile number is empty.

## Outcome

Nothing is sent.
