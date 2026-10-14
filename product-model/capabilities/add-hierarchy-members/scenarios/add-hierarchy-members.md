---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Admin chooses + on a Manager''s row and picks two Sales Users'
  kind: actor
  actor: admin
  entities:
  - entity: hierarchy-entry
    effect: reads
    facts:
    - Person
  - entity: crm-user
    effect: reads
    facts:
    - Full name
  - entity: sales-user
    effect: reads
    facts: []
  - entity: manager
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sales-hierarchy'
- text: The Product places both under that Manager
  kind: product
  actor: admin
  entities:
  - entity: hierarchy-entry
    effect: creates
    facts:
    - Person
    - Reports to
  - entity: manager
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sales-hierarchy'
---

# Add people under a Manager

## Trigger

An Admin builds a team in the tree.

## Outcome

The two Sales Users report to the Manager: 2 users added to hierarchy.

## Edge cases

- The picker offers only people not yet in the tree whose role may sit under that person
- Add User at the top places people at the top level
