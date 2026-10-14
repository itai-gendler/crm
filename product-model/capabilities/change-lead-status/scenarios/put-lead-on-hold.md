---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets the lead''s status to Awaiting Reply, a configured status of the On Hold type'
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    from: Ongoing
    to: On Hold
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Put a lead on hold

## Trigger

A Sales User waits on a lead.

## Outcome

The lead is on hold until someone moves it on.
