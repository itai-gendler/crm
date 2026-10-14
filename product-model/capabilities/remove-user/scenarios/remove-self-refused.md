---
kind: validation
routes:
  main: Administration
steps:
- text: The Manager chooses Remove on their own row
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
- text: 'The Product refuses: You cannot remove yourself'
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

# Remove oneself

## Trigger

A Manager tries to remove their own access.

## Outcome

Nothing changes.
