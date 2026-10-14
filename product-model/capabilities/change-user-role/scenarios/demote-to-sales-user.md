---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Manager picks Sales User in a colleague''s role menu'
  kind: actor
  actor: manager
  entities:
  - entity: crm-user
    effect: changes
    from: Manager
    to: Sales User
    facts: []
  - entity: sales-user
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::users'
---

# Make a Manager a Sales User

## Trigger

A Manager narrows a colleague's access.

## Outcome

The colleague is a Sales User, limited to the CRM, and sees only their own and assigned leads and deals.
