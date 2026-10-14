---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Delete on a contact and unlinks the deals they are on
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    facts:
    - Contacts
    - Primary email
    - Primary mobile no
  - entity: contact
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::contact'
- text: The Sales User confirms deleting the contact
  kind: actor
  actor: sales-user
  entities:
  - entity: contact
    effect: removes
  contexts:
    main:
      place: 'crm-web::sales-workspace::contact'
---

# Delete a contact

## Trigger

A Sales User deletes a contact.

## Outcome

The contact is gone and no longer on any deal.
