---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User chooses Remove on one of the deal''s contacts'
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
- text: 'The Product clears the deal''s primary email and mobile when the primary contact was removed'
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

# Remove a contact from a deal

## Trigger

A Sales User removes someone no longer involved.

## Outcome

The contact is no longer on the deal: Contact Removed.
