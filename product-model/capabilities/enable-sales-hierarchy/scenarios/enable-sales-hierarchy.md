---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager chooses Enable on Sales Hierarchy
  kind: actor
  actor: manager
  entities:
  - entity: crm-settings
    effect: changes
    facts:
    - Sales hierarchy
  contexts:
    main:
      place: 'crm-web::administration::sales-hierarchy'
---

# Enable the sales hierarchy

## Trigger

A Manager wants visibility to follow the reporting lines.

## Outcome

Sales hierarchy enabled; Managers in the tree now see only their team's leads and deals.
