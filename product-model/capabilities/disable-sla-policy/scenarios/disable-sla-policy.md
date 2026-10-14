---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager switches a policy that is not the default off
  kind: actor
  actor: manager
  entities:
  - entity: sla-policy
    effect: changes
    from: Enabled
    to: Disabled
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sla-policies'
---

# Disable an SLA policy

## Trigger

A Manager pauses a policy.

## Outcome

The policy is no longer given to leads or deals; those that already have it keep it.
