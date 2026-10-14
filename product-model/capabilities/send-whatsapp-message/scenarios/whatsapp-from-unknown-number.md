---
kind: primary
routes:
  main: WhatsApp
steps:
- text: 'The Prospect messages the business from a number no contact, lead or deal has'
  kind: actor
  actor: prospect
  entities:
  - entity: whatsapp-message
    effect: creates
    facts:
    - Message
    - Direction
    - Phone number
  - entity: lead
    effect: reads
    facts: []
  - entity: deal
    effect: reads
    facts: []
  - entity: contact
    effect: reads
    facts: []
  contexts:
    main:
      place: whatsapp
- text: 'The Product creates a lead from the sender''s number and profile name, from source WhatsApp, and files the message on it'
  kind: product
  entities:
  - entity: lead
    effect: creates
    to: Open
    facts:
    - Mobile no.
    - First name
    - Source
    - Status
    - Communication status
  - entity: whatsapp-message
    effect: changes
    facts:
    - Linked to
  contexts:
    main:
      place: whatsapp
---

# An unknown number messages the business

## Trigger

A stranger writes to the business on WhatsApp through an account that appends incoming messages to leads.

## Outcome

A new lead holds the number and the message.

## Edge cases

- An account that does not append incoming messages to leads keeps the message without a lead
