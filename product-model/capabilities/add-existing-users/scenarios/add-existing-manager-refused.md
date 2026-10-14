---
kind: validation
routes:
  main: Administration
steps:
- text: The Manager asks for the Manager role for an existing person
  kind: actor
  actor: manager
  entities:
  - entity: crm-user
    effect: reads
    facts:
    - Email
  contexts:
    main:
      place: 'crm-web::administration::users'
- text: 'The Product refuses: Only System Managers can assign the Sales Manager role'
  kind: condition
  actor: manager
  entities:
  - entity: crm-user
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::users'
---

# A Manager adds someone as Manager

## Trigger

A Manager tries to add a peer Manager.

## Outcome

The person's roles are unchanged.
