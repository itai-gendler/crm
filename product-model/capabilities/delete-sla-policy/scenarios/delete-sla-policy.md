---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager deletes a policy
  kind: actor
  actor: manager
  entities:
  - entity: sla-policy
    effect: removes
    from: Disabled
  contexts:
    main:
      place: 'crm-web::administration::sla-policies'
---

# Delete an SLA policy

## Trigger

A Manager retires a policy.

## Outcome

SLA policy deleted.
