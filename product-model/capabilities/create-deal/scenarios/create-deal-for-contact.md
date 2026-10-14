---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User chooses New Deal on a contact''s page'
  kind: actor
  actor: sales-user
  entities:
  - entity: contact
    effect: reads
    facts:
    - Full name
    - Organization
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::contact'
- text: The Sales User sets the status and value and creates the deal
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
- text: The Product opens the new deal
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Create a deal for an existing contact

## Trigger

A Sales User starts a deal for someone already in Contacts.

## Outcome

The new deal has the contact as its primary contact and their organization.
