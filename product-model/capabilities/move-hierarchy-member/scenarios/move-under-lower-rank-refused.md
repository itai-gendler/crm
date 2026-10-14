---
kind: validation
routes:
  main: Administration
steps:
- text: 'The Admin drags a Manager''s row onto a Sales User'
  kind: actor
  actor: admin
  entities:
  - entity: hierarchy-entry
    effect: reads
    facts:
    - Person
  - entity: sales-user
    effect: reads
    facts: []
  - entity: manager
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sales-hierarchy'
- text: The Product does not allow the drop
  kind: condition
  actor: admin
  entities:
  - entity: hierarchy-entry
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sales-hierarchy'
---

# Move a Manager under a Sales User

## Trigger

An Admin tries to put a Manager under a Sales User.

## Outcome

The tree is unchanged.

## Edge cases

- Dropping someone under one of their own reports is refused the same way
