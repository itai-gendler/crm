---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Manager names a policy, picks what it applies on, sets a four-hour first response for Open, working hours Monday to Friday and a holiday list, and saves'
  kind: actor
  actor: manager
  entities:
  - entity: sla-policy
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
      place: 'crm-web::administration::sla-policy'
---

# Create an SLA policy

## Trigger

A Manager sets a response target for new leads.

## Outcome

SLA policy created; matching leads created or saved from now on get a response deadline.
