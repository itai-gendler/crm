---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User sets another mobile number as primary on a contact who is primary on deals
  kind: actor
  actor: sales-user
  entities:
  - entity: contact
    effect: changes
    facts:
    - Phone numbers
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::contact'
- text: 'The Product copies the new primary email and mobile to every deal where the contact is primary, recording the change on each'
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    facts:
    - Primary mobile no
    - Primary email
  - entity: contact
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::contact'
---

# Change the mobile number of a deal's primary contact

## Trigger

A Sales User updates a contact's main number.

## Outcome

Every deal with this primary contact now calls and messages the new number.

## Edge cases

- A deal with a WhatsApp conversation on the old number asks for confirmation first
