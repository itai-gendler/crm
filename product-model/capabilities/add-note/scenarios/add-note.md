---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User chooses New Note on the lead, writes a title and content mentioning a colleague, and creates it'
  kind: actor
  actor: sales-user
  entities:
  - entity: note
    effect: creates
    facts:
    - Title
    - Content
    - Linked to
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product shows it on the lead''s Notes tab and notifies the mentioned colleague'
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
  - entity: lead
    effect: reads
    facts: []
  - entity: note
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Add a note to a lead

## Trigger

A Sales User records what they learned about a lead.

## Outcome

The note is on the lead and the colleague has a Mention notification.
