---
kind: validation
routes:
  main: Sales workspace
steps:
- text: Forecasting is on
  kind: condition
  actor: sales-user
  entities:
  - entity: crm-settings
    effect: reads
    facts:
    - Forecasting
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
- text: The Sales User creates a deal without an expected deal value
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts:
    - Expected deal value
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
- text: 'The Product refuses: Expected deal value is required'
  kind: condition
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
---

# Create a deal without forecast values while forecasting is on

## Trigger

A Sales User creates a deal without forecasting values.

## Outcome

No deal is created.

## Edge cases

- A missing expected closure date is refused the same way
