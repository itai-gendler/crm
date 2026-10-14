---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager chooses Remove on a Sales User and confirms
  kind: actor
  actor: manager
  entities:
  - entity: crm-user
    effect: changes
    from: Sales User
    to: Without CRM access
    facts: []
  - entity: hierarchy-entry
    effect: removes
  - entity: sales-user
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::users'
---

# Remove a user

## Trigger

A Manager offboards a salesperson.

## Outcome

The person no longer has a CRM role or a place in the hierarchy; their site account remains.
