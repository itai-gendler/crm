---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Delete on an organization and confirms
  kind: actor
  actor: sales-user
  entities:
  - entity: organization
    effect: removes
  contexts:
    main:
      place: 'crm-web::sales-workspace::organization'
---

# Delete an organization

## Trigger

A Sales User deletes an organization.

## Outcome

The organization is gone.
