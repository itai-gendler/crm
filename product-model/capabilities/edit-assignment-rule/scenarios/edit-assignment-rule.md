---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager picks Assign by workload on a rule and saves
  kind: actor
  actor: manager
  entities:
  - entity: assignment-rule
    effect: changes
    facts:
    - Routing
  contexts:
    main:
      place: 'crm-web::administration::assignment-rule'
---

# Switch a rule to assign by workload

## Trigger

A Manager balances the load.

## Outcome

The rule assigns each new match to the assignee with the fewest open assignments.
