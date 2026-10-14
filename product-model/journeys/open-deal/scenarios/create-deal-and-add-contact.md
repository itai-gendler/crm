---
kind: primary
result: achieved
routes:
  main: Sales workspace
steps:
- text: The Sales User creates the deal for an existing organization and contact
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
  - entity: contact
    effect: reads
    facts: []
  - entity: organization
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
  capability: create-deal
- text: 'The Product opens the new deal''s page'
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
  capability: create-deal
- text: The Sales User adds a second contact to the deal
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    facts:
    - Contacts
  - entity: contact
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
  capability: add-deal-contact
---

# Create a deal and add a contact

## Trigger

A Sales User creates a deal on Deals.

## Outcome

The Sales User is on the deal, which has two contacts.
