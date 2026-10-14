---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Make a Call on a lead with a mobile number
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Mobile no.
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: The Product places the call through the calling medium and records an outgoing call log on the lead
  kind: product
  actor: sales-user
  entities:
  - entity: call-log
    effect: creates
    facts:
    - Type
    - Status
    - Caller
    - From
    - To
    - Medium
    - Start time
    - Linked to
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product updates the call log''s status, duration and recording as the provider reports them'
  kind: product
  actor: sales-user
  entities:
  - entity: call-log
    effect: changes
    facts:
    - Status
    - Duration
    - Recording
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Call a lead

## Trigger

A Sales User calls a lead from the CRM.

## Outcome

The call shows on the lead's Calls tab with its outcome, and its recording when one is kept.

## Edge cases

- A lead with no mobile number → Please set a mobile number to make calls
- With no calling medium enabled, Make a Call is not offered

## Decision points

### Medium

Which calling medium does the Sales User use?

- Twilio → the call runs in the browser
- Exotel → the provider rings the Sales User's phone first
