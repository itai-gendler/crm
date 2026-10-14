---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Admin chooses Delete on a Manager with reports, then Unlink & Delete'
  kind: actor
  actor: admin
  entities:
  - entity: hierarchy-entry
    as: head
    effect: removes
  - entity: hierarchy-entry
    as: report
    effect: removes
    with: head
  - entity: manager
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sales-hierarchy'
---

# Remove a Manager with their whole team

## Trigger

An Admin takes a whole branch out of the tree.

## Outcome

The Manager and everyone below them are out of the tree.
