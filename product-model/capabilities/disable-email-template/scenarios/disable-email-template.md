---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User switches a template''s Enabled off'
  kind: actor
  actor: sales-user
  entities:
  - entity: email-template
    effect: changes
    from: Enabled
    to: Disabled
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::email-templates'
---

# Disable an email template

## Trigger

A Sales User retires a template.

## Outcome

The template is no longer offered.
