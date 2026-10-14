---
kind: primary
routes:
  main: Administration
steps:
- text: The Admin chooses Disable on Sales Hierarchy and confirms
  kind: actor
  actor: admin
  entities:
  - entity: crm-settings
    effect: changes
    facts:
    - Sales hierarchy
  contexts:
    main:
      place: 'crm-web::administration::sales-hierarchy'
---

# Disable the sales hierarchy

## Trigger

An Admin stops restricting visibility by the tree.

## Outcome

Sales hierarchy disabled; every Manager sees every lead and deal again and the tree is kept.
