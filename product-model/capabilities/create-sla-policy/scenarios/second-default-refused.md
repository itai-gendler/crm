---
kind: validation
routes:
  main: Administration
steps:
- text: A default policy for the same record type exists
  kind: condition
  actor: manager
  entities:
  - entity: sla-policy
    effect: reads
    facts:
    - Default
    - Apply on
  contexts:
    main:
      place: 'crm-web::administration::sla-policy'
- text: The Manager saves another policy for that record type set as default
  kind: actor
  actor: manager
  entities:
  - entity: sla-policy
    effect: reads
    facts:
    - Default
  contexts:
    main:
      place: 'crm-web::administration::sla-policy'
- text: 'The Product refuses: a default Service Level Agreement already exists for that record type'
  kind: condition
  actor: manager
  entities:
  - entity: sla-policy
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::sla-policy'
---

# Create a second default policy

## Trigger

A Manager marks a second policy as default for the same record type.

## Outcome

The policy is not saved.
