---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager deletes a rule
  kind: actor
  actor: manager
  entities:
  - entity: assignment-rule
    effect: removes
    from: Disabled
  contexts:
    main:
      place: 'crm-web::administration::assignment-rules'
---

# Delete an assignment rule

## Trigger

A Manager retires a rule.

## Outcome

Assignment rule deleted.
