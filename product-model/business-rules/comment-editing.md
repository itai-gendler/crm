---
appliesTo:
- type: entity
  id: comment
  effect: changes
permits:
- related:
  - verb: writes
    entity: sales-user
- related:
  - verb: writes
    entity: manager
- related:
  - verb: writes
    entity: admin
references:
- kind: code
  role: implementation
  target: frontend/src/components/Activities/CommentArea.vue
---

# Only its author edits a comment

Edit is offered only on one's own comments.
