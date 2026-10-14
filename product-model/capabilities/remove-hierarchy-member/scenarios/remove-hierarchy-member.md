---
kind: primary
routes:
  main: Administration
steps:
- text: The Admin chooses Delete on a Sales User with no reports and confirms
  kind: actor
  actor: admin
  entities:
  - entity: hierarchy-entry
    effect: removes
  - entity: sales-user
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sales-hierarchy'
---

# Remove someone without reports

## Trigger

An Admin takes a salesperson out of the tree.

## Outcome

Removed from hierarchy.
