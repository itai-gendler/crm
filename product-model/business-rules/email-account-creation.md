---
appliesTo:
- type: entity
  id: email-account
  effect: creates
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Settings.vue
- kind: code
  role: implementation
  target: crm/api/settings.py
---

# Managers and Admins add email accounts

Only Managers and Admins connect email accounts.
