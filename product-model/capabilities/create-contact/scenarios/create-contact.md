---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User enters a name, email, mobile number and company and creates the contact'
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
---

# Create a contact

## Trigger

A Sales User chooses Create on Contacts.

## Outcome

The Sales User is on the new contact's page; the email and mobile entered are primary.

## Edge cases

- A field the contact form requires left empty → is required
