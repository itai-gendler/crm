---
kind: primary
result: achieved
routes:
  main: Sales workspace
steps:
- text: The Sales User creates the contact
  kind: actor
  actor: sales-user
  entities:
  - entity: contact
    effect: creates
    facts:
    - First name
    - Last name
    - Email addresses
    - Phone numbers
    - Organization
  contexts:
    main:
      place: 'crm-web::sales-workspace::contacts'
  capability: create-contact
- text: 'The Product opens the new contact''s page'
  kind: product
  actor: sales-user
  entities:
  - entity: contact
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::contact'
  capability: create-contact
- text: The Sales User chooses New Deal there and creates the deal
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: creates
    to: Open
    facts:
    - Organization
    - Status
    - Deal owner
    - Deal value
    - Expected deal value
    - Expected closure date
    - Contacts
    - Primary email
    - Primary mobile no
  contexts:
    main:
      place: 'crm-web::sales-workspace::contact'
  capability: create-deal
---

# Create a contact, then a deal for them

## Trigger

A Sales User creates a contact on Contacts.

## Outcome

The contact is the primary contact of a new deal.
