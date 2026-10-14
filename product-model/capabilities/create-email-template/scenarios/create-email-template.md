---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User enters a name, picks the record type it is for, writes the subject and content and saves'
  kind: actor
  actor: sales-user
  entities:
  - entity: email-template
    effect: creates
    to: Disabled
    facts:
    - Name
    - For
    - Subject
    - Content type
    - Content
  contexts:
    main:
      place: 'crm-web::sales-workspace::email-templates'
---

# Create an email template

## Trigger

A Sales User wants a reusable email.

## Outcome

The template exists, disabled until someone enables it.

## Edge cases

- Name, subject or content left empty → is required
- Switching Enabled on before saving creates it enabled
