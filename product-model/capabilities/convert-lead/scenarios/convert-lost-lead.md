---
kind: validation
routes:
  main: Sales workspace
steps:
- text: 'The lead''s status is of the Lost type'
  kind: condition
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: The Sales User looks for Convert to Deal on the lead
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Status
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product offers no conversion: Cannot convert a lost lead to deal'
  kind: condition
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Status
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Convert a lost lead

## Trigger

A Sales User wants to convert a lead marked lost.

## Outcome

No deal is created; the lead stays lost.
