---
kind: validation
routes:
  main: Administration
steps:
- text: The colleague heads a branch of the sales hierarchy
  kind: condition
  actor: manager
  entities:
  - entity: hierarchy-entry
    effect: reads
    facts:
    - Reports to
  contexts:
    main:
      place: 'crm-web::administration::users'
- text: 'The Manager picks Sales User in that colleague''s role menu'
  kind: actor
  actor: manager
  entities:
  - entity: crm-user
    effect: reads
    facts:
    - Full name
  - entity: sales-user
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::users'
- text: 'The Product refuses: remove this user from the sales hierarchy before changing their role to Sales User'
  kind: condition
  actor: manager
  entities:
  - entity: crm-user
    effect: reads
    facts: []
  - entity: sales-user
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::users'
---

# Make a sales hierarchy's head a Sales User

## Trigger

A Manager demotes someone with direct reports, or at the top of the tree.

## Outcome

The colleague keeps the Manager role.
