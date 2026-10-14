---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager chooses Duplicate on a policy and names the copy
  kind: actor
  actor: manager
  entities:
  - entity: sla-policy
    as: original
    effect: reads
    facts:
    - Name
  - entity: sla-policy
    as: copy
    effect: creates
    to: Enabled
    facts:
    - Name
    - Apply on
    - Default
    - Conditions
    - Priorities
    - Working hours
    - Holiday list
    - Rolling responses
  contexts:
    main:
      place: 'crm-web::administration::sla-policies'
---

# Duplicate an SLA policy

## Trigger

A Manager starts a policy for deals from the one for leads.

## Outcome

SLA policy duplicated.
