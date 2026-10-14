---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens Contacts
  kind: actor
  actor: sales-user
  entities:
  - entity: contact
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::contacts'
- text: 'The Product lists contacts with their email, phone and company'
  kind: product
  actor: sales-user
  entities:
  - entity: contact
    effect: reads
    facts:
    - Full name
    - Email addresses
    - Phone numbers
    - Organization
  contexts:
    main:
      place: 'crm-web::sales-workspace::contacts'
---

# Browse contacts

## Trigger

A Sales User opens Contacts from the sidebar.

## Outcome

The Sales User sees the contacts.
