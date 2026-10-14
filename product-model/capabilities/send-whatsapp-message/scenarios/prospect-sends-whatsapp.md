---
kind: primary
routes:
  main: WhatsApp
steps:
- text: The Prospect sends a WhatsApp message to the business number
  kind: actor
  actor: prospect
  entities:
  - entity: whatsapp-message
    effect: creates
    facts:
    - Message
    - Direction
    - Phone number
  contexts:
    main:
      place: whatsapp
- text: The Product finds the deal with that mobile number and files the message on it
  kind: product
  entities:
  - entity: deal
    effect: reads
    facts:
    - Primary mobile no
  - entity: whatsapp-message
    effect: changes
    facts:
    - Linked to
  contexts:
    main:
      place: whatsapp
- text: 'The Product notifies the deal''s assignees'
  kind: product
  entities:
  - entity: notification
    effect: creates
    facts:
    - Type
    - From
    - Message
    - Read
    - Linked to
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: whatsapp
---

# A prospect messages the business on WhatsApp

## Trigger

A prospect writes to the business on WhatsApp.

## Outcome

The message shows on the deal's WhatsApp tab and its assignees have a WhatsApp notification.

## Edge cases

- Numbers match whatever their formatting
