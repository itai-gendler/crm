---
kind: validation
routes:
  main: Administration
steps:
- text: The Manager switches on a rule with no assignees
  kind: actor
  actor: manager
  entities:
  - entity: assignment-rule
    effect: reads
    facts:
    - Assignees
  contexts:
    main:
      place: 'crm-web::administration::assignment-rules'
- text: 'The Product refuses: Cannot enable rule without adding users in it'
  kind: condition
  actor: manager
  entities:
  - entity: assignment-rule
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::assignment-rules'
---

# Enable a rule with no assignees

## Trigger

A Manager enables an empty rule.

## Outcome

The rule stays disabled.
