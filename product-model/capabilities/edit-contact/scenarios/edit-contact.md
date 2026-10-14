---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User adds an email address to the contact and sets it as primary
  kind: actor
  actor: sales-user
  entities:
  - entity: contact
    effect: changes
    facts:
    - Email addresses
  contexts:
    main:
      place: 'crm-web::sales-workspace::contact'
---

# Add an email address and make it primary

## Trigger

A Sales User records a contact's new email address.

## Outcome

The contact's primary email is the new address.
