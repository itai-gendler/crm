---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Manager chooses Make Public on a view
  kind: actor
  actor: manager
  entities:
  - entity: view
    effect: changes
    facts:
    - Public
    - Pinned
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
---

# Make a view public

## Trigger

A Manager shares a view with the team.

## Outcome

Everyone sees the view under Public Views; it is no longer anyone's pinned private view.
