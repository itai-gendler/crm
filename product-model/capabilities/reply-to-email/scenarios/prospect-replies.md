---
kind: primary
routes:
  main: Email inbox
steps:
- text: The Prospect replies to an email sent from a lead
  kind: actor
  actor: prospect
  entities:
  - entity: email-message
    effect: creates
    facts:
    - Subject
    - Content
    - From
    - To
    - Direction
    - Sent at
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: email-inbox
- text: 'The Product files the reply on the lead''s timeline'
  kind: product
  entities:
  - entity: email-message
    effect: changes
    facts:
    - Linked to
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: email-inbox
---

# A prospect replies by email

## Trigger

A prospect answers an email the sales team sent from a lead.

## Outcome

The reply shows on the lead's Emails and Activity tabs.

## Decision points

### Reopen

Is Reopen lead/deal on new communication on?

- On → the lead's communication status goes back to Open
- Off → it is left as it was

### Modified time

Is Update timestamp on new communication on?

- On → the lead counts as just modified
- Off → its modified time is unchanged
