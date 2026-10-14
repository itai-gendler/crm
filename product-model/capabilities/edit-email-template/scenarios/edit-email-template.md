---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User changes a template''s subject and content and saves'
  kind: actor
  actor: sales-user
  entities:
  - entity: email-template
    effect: changes
    facts:
    - Subject
    - Content
  contexts:
    main:
      place: 'crm-web::sales-workspace::email-templates'
---

# Edit an email template

## Trigger

A Sales User improves a template.

## Outcome

The template holds the new text.
