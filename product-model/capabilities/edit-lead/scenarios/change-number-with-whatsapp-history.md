---
kind: edge
routes:
  main: Sales workspace
steps:
- text: The Sales User changes the mobile number of a lead with a WhatsApp conversation
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Mobile no.
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product asks for confirmation, saying the old number''s replies will no longer show on the lead'
  kind: condition
  actor: sales-user
  entities:
  - entity: whatsapp-message
    effect: reads
    facts:
    - Phone number
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: The Sales User confirms the change
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
---

# Change a lead's mobile number while it has WhatsApp messages

## Trigger

A Sales User edits the Mobile No. of a lead that has WhatsApp messages with the old number.

## Outcome

After confirming, new WhatsApp messages go to the new number; replies from the old number stop showing on the lead.

## Edge cases

- Clearing the number warns that the lead can no longer be messaged
