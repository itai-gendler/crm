---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Admin picks Admin in a Manager''s role menu'
  kind: actor
  actor: admin
  entities:
  - entity: crm-user
    effect: changes
    from: Manager
    to: Admin
    facts: []
  - entity: manager
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::users'
---

# Make a Manager an Admin

## Trigger

An Admin shares the running of the CRM.

## Outcome

The person holds the System Manager role with Sales Manager and Sales User, and reaches every module.
