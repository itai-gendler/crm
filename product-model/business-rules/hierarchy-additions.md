---
appliesTo:
- type: entity
  id: hierarchy-entry
  effect: creates
  contexts:
  - place: 'crm-web::administration::sales-hierarchy'
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Hierarchy/Hierarchy.vue
- kind: code
  role: implementation
  target: docs/user-hierarchy.md
---

# Only an Admin adds people to the sales hierarchy

Managers see the sales hierarchy read-only; Admins edit it.
