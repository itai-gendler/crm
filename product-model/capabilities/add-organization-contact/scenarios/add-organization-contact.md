---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Add Contact on the organization and picks a contact
  kind: actor
  actor: sales-user
  entities:
  - entity: organization
    effect: reads
    facts:
    - Organization name
  - entity: contact
    effect: changes
    facts:
    - Organization
  contexts:
    main:
      place: 'crm-web::sales-workspace::organization'
---

# Add a contact to an organization

## Trigger

A Sales User records that someone works at an organization.

## Outcome

The contact belongs to the organization and shows under its contacts.
