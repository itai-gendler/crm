---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User picks a contact in the deal''s Contacts section'
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
- text: The Product makes a sole contact primary and copies their email and mobile to the deal
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

# Add a contact to a deal

## Trigger

A Sales User adds someone involved in the deal.

## Outcome

The contact is on the deal: Contact Added.

## Edge cases

- A contact already on the deal → Contact Already Added
