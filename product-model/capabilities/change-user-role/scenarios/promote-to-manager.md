---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Admin picks Manager in a Sales User''s role menu'
  kind: actor
  actor: admin
  entities:
  - entity: crm-user
    effect: changes
    from: Sales User
    to: Manager
    facts: []
  - entity: sales-user
    effect: reads
    facts: []
  - entity: manager
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::users'
---

# Make a Sales User a Manager

## Trigger

An Admin promotes a salesperson.

## Outcome

The person holds the Manager role; their user role changed successfully.
