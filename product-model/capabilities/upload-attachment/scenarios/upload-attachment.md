---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Upload Attachment on the deal and adds a file
  kind: actor
  actor: sales-user
  entities:
  - entity: attachment
    effect: creates
    facts:
    - File
    - Private
    - Linked to
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Upload an attachment

## Trigger

A Sales User keeps a document with a deal.

## Outcome

The file is on the deal's Attachments tab.

## Edge cases

- A file over the site's size limit or of a type it does not allow is refused
