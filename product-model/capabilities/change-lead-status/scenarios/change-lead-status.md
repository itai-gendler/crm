---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets the lead''s status to Nurture'
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    from: Open
    to: Ongoing
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The lead''s activity shows the change'
  kind: condition
  actor: sales-user
  entities:
  - entity: activity
    effect: reads
    facts:
    - Actor
    - Change
    - Time
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Move a lead to another status

## Trigger

A Sales User picks a status from the lead's status menu.

## Outcome

The lead is in Nurture and the change shows in its activity with how long it spent in the previous status.
