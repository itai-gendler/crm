---
availability:
- place: 'crm-web::administration'
domain: email-accounts
references:
- kind: code
  role: implementation
  target: crm/api/settings.py
- kind: code
  role: implementation
  target: frontend/src/components/Settings/EmailAdd.vue
- kind: code
  role: implementation
  target: frontend/src/components/Settings/EmailEdit.vue
---

# Edit email account

Change an email account's name, credentials and directions.
