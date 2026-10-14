---
appliesTo:
- type: entity
  id: assignment-rule
  effect: changes
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Settings.vue
---

# Managers and Admins change assignment rules

Assignment rules are open only to Managers and Admins, in Settings.
