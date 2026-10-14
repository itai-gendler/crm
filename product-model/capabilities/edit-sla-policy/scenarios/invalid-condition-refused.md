---
kind: validation
routes:
  main: Administration
steps:
- text: The Manager writes a condition that cannot be evaluated and saves
  kind: actor
  actor: manager
  entities:
  - entity: sla-policy
    effect: reads
    facts:
    - Conditions
  contexts:
    main:
      place: 'crm-web::administration::sla-policy'
- text: 'The Product refuses: The Condition is invalid'
  kind: condition
  actor: manager
  entities:
  - entity: sla-policy
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sla-policy'
---

# Save an SLA policy with an invalid condition

## Trigger

A Manager mistypes a policy condition.

## Outcome

The policy keeps its previous condition.
