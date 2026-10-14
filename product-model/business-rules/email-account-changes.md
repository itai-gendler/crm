---
appliesTo:
- type: entity
  id: email-account
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

# Managers and Admins change email accounts

Only Managers and Admins change email accounts.
