---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Set As Default on the Kanban view of Deals
  kind: actor
  actor: sales-user
  entities:
  - entity: view
    effect: changes
    facts:
    - Default
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
---

# Set the default view

## Trigger

A Sales User prefers the board.

## Outcome

Deals opens on the board for the Sales User; their other views of Deals are no longer default.
