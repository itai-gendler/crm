---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens Call Logs
  kind: actor
  actor: sales-user
  entities:
  - entity: call-log
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::call-logs'
- text: 'The Product lists calls with caller, receiver, type, status and duration'
  kind: product
  actor: sales-user
  entities:
  - entity: call-log
    effect: reads
    facts:
    - Caller
    - Receiver
    - Type
    - Status
    - Duration
    - From
    - To
  contexts:
    main:
      place: 'crm-web::sales-workspace::call-logs'
- text: The Sales User opens a call and listens to its recording
  kind: actor
  actor: sales-user
  entities:
  - entity: call-log
    effect: reads
    facts:
    - Recording
    - Call notes
    - Call tasks
    - Linked to
  contexts:
    main:
      place: 'crm-web::sales-workspace::call-logs'
---

# Review a call

## Trigger

A Sales User looks back at calls.

## Outcome

The Sales User has heard the call and seen its notes and tasks.

## Edge cases

- Notes, tasks and the lead or deal the person may not see are left out of the call's details
