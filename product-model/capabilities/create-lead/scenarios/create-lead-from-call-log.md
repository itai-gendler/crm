---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens a call log with no lead or deal and chooses to create a lead
  kind: actor
  actor: sales-user
  entities:
  - entity: call-log
    effect: reads
    facts:
    - From
    - Linked to
  - entity: lead
    effect: reads
    facts: []
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::call-logs'
- text: 'The Product creates a lead owned by the Sales User with the caller''s number, and links the call log to it'
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: creates
    to: Open
    facts:
    - First name
    - Mobile no.
    - Lead owner
    - Status
    - Communication status
  - entity: call-log
    effect: changes
    facts:
    - Linked to
  contexts:
    main:
      place: 'crm-web::sales-workspace::call-logs'
---

# Create a lead from a call with an unknown number

## Trigger

A Sales User reviews a call from a number the CRM does not know.

## Outcome

A new lead, named after the call when no name is given, holds the caller's number and the call log is linked to it.
