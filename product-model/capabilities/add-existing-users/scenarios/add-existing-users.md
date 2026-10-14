---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Manager chooses Add Existing User, picks two people and the Sales User role'
  kind: actor
  actor: manager
  entities:
  - entity: crm-user
    effect: reads
    facts:
    - Full name
    - Email
  - entity: sales-user
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::users'
- text: 'The Product gives each person the Sales User role, limited to the CRM'
  kind: product
  actor: manager
  entities:
  - entity: crm-user
    effect: changes
    from: Without CRM access
    to: Sales User
    facts: []
  - entity: sales-user
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::users'
---

# Add existing users as Sales Users

## Trigger

A Manager brings colleagues who already use the site into the CRM.

## Outcome

Both people can open the CRM as Sales Users: Users Added Successfully.
