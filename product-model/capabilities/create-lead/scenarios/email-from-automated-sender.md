---
kind: edge
routes:
  main: Email inbox
steps:
- text: 'The Prospect''s system sends an email from a no-reply or mailer-daemon address'
  kind: actor
  actor: prospect
  entities:
  - entity: email-message
    effect: creates
    facts:
    - From
    - Subject
    - Content
    - Direction
    - Sent at
  contexts:
    main:
      place: email-inbox
- text: The Product starts no lead for an automated sender
  kind: condition
  entities:
  - entity: email-message
    effect: reads
    facts:
    - From
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: email-inbox
---

# An automated sender emails the business

## Trigger

An email arrives from an address like noreply@ or mailer-daemon@.

## Outcome

The email is kept but no lead is created for it.

## Edge cases

- An email from an address that already belongs to a lead starts no new lead either
