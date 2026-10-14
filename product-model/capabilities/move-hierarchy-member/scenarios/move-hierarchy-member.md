---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Admin drags a Sales User''s row onto another Manager'
  kind: actor
  actor: admin
  entities:
  - entity: hierarchy-entry
    effect: changes
    facts:
    - Reports to
  - entity: sales-user
    effect: reads
    facts: []
  - entity: manager
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sales-hierarchy'
---

# Move someone under another Manager

## Trigger

An Admin moves a salesperson to another team.

## Outcome

The Sales User reports to the new Manager: Updated reports to.

## Edge cases

- Move to top level makes them report to no one
