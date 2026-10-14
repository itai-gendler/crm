---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Admin chooses Delete on a Manager with reports, then Delete Only User'
  kind: actor
  actor: admin
  entities:
  - entity: hierarchy-entry
    as: report
    effect: changes
    facts:
    - Reports to
  - entity: hierarchy-entry
    as: head
    effect: removes
  - entity: manager
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sales-hierarchy'
---

# Remove a Manager and keep their reports

## Trigger

An Admin removes a Manager whose team stays.

## Outcome

The Manager's direct reports now report to the Manager's own manager, or to no one.
