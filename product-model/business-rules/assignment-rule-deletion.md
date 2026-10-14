---
appliesTo:
- type: entity
  id: assignment-rule
  effect: removes
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Settings.vue
---

# Managers and Admins delete assignment rules

Assignment rules are open only to Managers and Admins, in Settings.
