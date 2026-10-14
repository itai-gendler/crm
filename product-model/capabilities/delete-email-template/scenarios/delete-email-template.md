---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User deletes a template
  kind: actor
  actor: sales-user
  entities:
  - entity: email-template
    effect: removes
    from: Disabled
  contexts:
    main:
      place: 'crm-web::sales-workspace::email-templates'
---

# Delete an email template

## Trigger

A Sales User removes an unused template.

## Outcome

The template is gone.
