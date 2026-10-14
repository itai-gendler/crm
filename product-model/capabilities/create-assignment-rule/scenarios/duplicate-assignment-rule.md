---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager chooses Duplicate on a rule and names the copy
  kind: actor
  actor: manager
  entities:
  - entity: assignment-rule
    as: original
    effect: reads
    facts:
    - Name
  - entity: assignment-rule
    as: copy
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
      place: 'crm-web::administration::assignment-rules'
---

# Duplicate an assignment rule

## Trigger

A Manager starts a rule from an existing one.

## Outcome

Assignment rule duplicated.
