---
kind: validation
routes:
  main: Sales workspace
steps:
- text: The Sales User leaves the first name empty and chooses Create
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - First name
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
- text: 'The Product refuses: First Name is mandatory'
  kind: condition
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
---

# Create a lead without a first name

## Trigger

A Sales User submits the new lead form without a first name.

## Outcome

No lead is created and the form stays open with the error.
