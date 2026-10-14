---
appliesTo:
- type: entity
  id: crm-settings
  effect: changes
  facts:
  - Update timestamp on new communication
  - Mark lead/deal as replied on response
  - Reopen lead/deal on new communication
  - Timeline timestamp format
  - Timeline sort order
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/GeneralSettings.vue
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Settings.vue
---

# Managers and Admins change the general settings

Only Managers and Admins change how communication touches records and how timelines read.
