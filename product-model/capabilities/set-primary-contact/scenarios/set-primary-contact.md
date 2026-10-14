---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User chooses Set as Primary Contact on one of the deal''s contacts'
  kind: actor
  actor: sales-user
  entities:
  - entity: contact
    effect: reads
    facts:
    - Full name
  - entity: deal
    effect: changes
    facts:
    - Contacts
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
- text: 'The Product copies that contact''s email and mobile to the deal'
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    facts:
    - Primary email
    - Primary mobile no
  - entity: contact
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Set a deal's primary contact

## Trigger

A Sales User changes who the main person on a deal is.

## Outcome

The chosen contact is primary and the deal's emails and calls go to them.
