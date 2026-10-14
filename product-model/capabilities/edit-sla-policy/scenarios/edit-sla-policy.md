---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Manager shortens a policy''s first response time and turns on rolling responses'
  kind: actor
  actor: manager
  entities:
  - entity: sla-policy
    effect: changes
    facts:
    - Priorities
    - Rolling responses
  contexts:
    main:
      place: 'crm-web::administration::sla-policy'
---

# Edit an SLA policy

## Trigger

A Manager tightens a policy.

## Outcome

SLA policy updated; deadlines not yet set use the new targets.
