---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User chooses Edit on their comment, changes it and saves'
  kind: actor
  actor: sales-user
  entities:
  - entity: comment
    effect: changes
    facts:
    - Content
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Edit a comment

## Trigger

A Sales User corrects their comment.

## Outcome

The comment shows the new text.
