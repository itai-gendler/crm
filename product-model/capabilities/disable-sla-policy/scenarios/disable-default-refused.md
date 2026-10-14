---
kind: validation
routes:
  main: Administration
steps:
- text: The Manager switches off the default policy
  kind: actor
  actor: manager
  entities:
  - entity: sla-policy
    effect: reads
    facts:
    - Default
  contexts:
    main:
      place: 'crm-web::administration::sla-policies'
- text: 'The Product refuses: An SLA set as default cannot be disabled'
  kind: condition
  actor: manager
  entities:
  - entity: sla-policy
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sla-policies'
---

# Disable the default SLA policy

## Trigger

A Manager tries to turn off the default policy.

## Outcome

The policy stays enabled.
