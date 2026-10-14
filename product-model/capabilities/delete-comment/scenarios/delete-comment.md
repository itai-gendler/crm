---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User deletes their comment and confirms
  kind: actor
  actor: sales-user
  entities:
  - entity: comment
    effect: removes
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Delete a comment

## Trigger

A Sales User removes their comment.

## Outcome

The comment is gone from the lead.
