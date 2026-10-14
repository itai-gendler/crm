---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager switches a rule off
  kind: actor
  actor: manager
  entities:
  - entity: assignment-rule
    effect: changes
    from: Enabled
    to: Disabled
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::assignment-rules'
---

# Disable an assignment rule

## Trigger

A Manager pauses automatic assignment.

## Outcome

The rule assigns nothing until enabled.
