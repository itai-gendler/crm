---
appliesTo:
- type: entity
  id: comment
  effect: removes
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

# Only its author deletes a comment

Delete is offered only on one's own comments.
