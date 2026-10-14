---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets the lead''s status to Unqualified'
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: The Sales User picks the lost reason Other and explains it
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    from: Ongoing
    to: Lost
    facts:
    - Status
    - Lost reason
    - Lost notes
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Mark a lead as lost

## Trigger

A Sales User moves a lead to a status of the Lost type.

## Outcome

The lead is Lost with its reason, and the lost reason shows in its side panel.
