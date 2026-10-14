---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Manager enters a name and description, picks what it applies on, a condition, Auto-rotate, three assignees and weekdays, and saves'
  kind: actor
  actor: manager
  entities:
  - entity: assignment-rule
    effect: creates
    to: Enabled
    facts:
    - Name
    - Description
    - Apply on
    - Priority
    - Assignment condition
    - Routing
    - Assignees
    - Assignment days
  contexts:
    main:
      place: 'crm-web::administration::assignment-rule'
---

# Create an assignment rule

## Trigger

A Manager wants new leads shared out automatically.

## Outcome

The rule is enabled and assigns new matching leads in turn.

## Edge cases

- Name, description, condition, assignees or days left empty → missing mandatory fields
