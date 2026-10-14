---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User changes the organization''s territory and address'
  kind: actor
  actor: sales-user
  entities:
  - entity: organization
    effect: changes
    facts:
    - Territory
    - Address
  contexts:
    main:
      place: 'crm-web::sales-workspace::organization'
---

# Edit an organization

## Trigger

A Sales User updates an organization.

## Outcome

The organization holds the new values.
