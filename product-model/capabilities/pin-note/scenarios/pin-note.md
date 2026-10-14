---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Pin to top on a note of the lead
  kind: actor
  actor: sales-user
  entities:
  - entity: note
    effect: changes
    facts:
    - Pinned
    - Pinned by
    - Pinned on
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Pin a note

## Trigger

A Sales User keeps an important note in view.

## Outcome

The note is first on the lead's Notes tab, Pinned by the Sales User, and the timeline says they pinned it.
