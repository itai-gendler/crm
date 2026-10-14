---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager switches a policy on
  kind: actor
  actor: manager
  entities:
  - entity: sla-policy
    effect: changes
    from: Disabled
    to: Enabled
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sla-policies'
---

# Enable an SLA policy

## Trigger

A Manager reactivates a policy.

## Outcome

SLA policy status updated; the policy applies again.
