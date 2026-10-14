---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User chooses Log a Call on the lead and enters the type, numbers, status and duration'
  kind: actor
  actor: sales-user
  entities:
  - entity: call-log
    effect: creates
    facts:
    - Type
    - Status
    - From
    - To
    - Duration
    - Linked to
    - Medium
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Log a call

## Trigger

A Sales User records a call they made from their own phone.

## Outcome

The call log is on the lead's Calls tab, recorded as Manual.
