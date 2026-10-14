---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User switches a template''s Enabled on'
  kind: actor
  actor: sales-user
  entities:
  - entity: email-template
    effect: changes
    from: Disabled
    to: Enabled
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::email-templates'
---

# Enable an email template

## Trigger

A Sales User makes a template available.

## Outcome

The template is offered when emailing deals.
