---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User opens the deal''s WhatsApp tab'
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts:
    - Primary mobile no
  - entity: whatsapp-message
    effect: reads
    facts:
    - Message
    - Direction
    - Media
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: The Sales User types a message and sends it
  kind: actor
  actor: sales-user
  entities:
  - entity: whatsapp-message
    effect: creates
    facts:
    - Message
    - Direction
    - Phone number
    - Linked to
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Send a WhatsApp message

## Trigger

A Sales User messages a deal's primary contact on WhatsApp.

## Outcome

The message is sent to the deal's mobile number and shows in the conversation.

## Edge cases

- A deal's conversation also shows the messages of the lead it came from

## Decision points

### Template

Does the Sales User send a template?

- Yes → the approved template is sent with the record's values
- No → the typed text is sent
