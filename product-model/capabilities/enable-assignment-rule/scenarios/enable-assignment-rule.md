---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager switches a rule with assignees on
  kind: actor
  actor: manager
  entities:
  - entity: assignment-rule
    effect: changes
    from: Disabled
    to: Enabled
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::assignment-rules'
---

# Enable an assignment rule

## Trigger

A Manager resumes automatic assignment.

## Outcome

The rule assigns again.
