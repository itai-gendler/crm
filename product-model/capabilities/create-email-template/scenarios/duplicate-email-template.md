---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User chooses Duplicate on a template, renames the copy and saves'
  kind: actor
  actor: sales-user
  entities:
  - entity: email-template
    as: original
    effect: reads
    facts:
    - Name
    - Subject
  - entity: email-template
    as: copy
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

# Duplicate an email template

## Trigger

A Sales User starts a template from an existing one.

## Outcome

A disabled copy exists.
