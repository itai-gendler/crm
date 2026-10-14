---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User sets the lead''s communication status to Replied'
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Communication status
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The lead''s first response is due'
  kind: condition
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - SLA status
    - Response by
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product records the first response and its working time, and the SLA as Fulfilled or Failed'
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - First responded on
    - First response time
    - SLA status
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Mark a lead as replied

## Trigger

A Sales User has answered a lead outside the CRM.

## Outcome

The lead's SLA shows the first response as fulfilled in its working time, or failed when the deadline had passed.

## Decision points

### Rolling responses

Does the lead's SLA policy time rolling responses?

- Yes → each later answer is timed too, and setting Open starts a new response deadline
- No → only the first response is timed
