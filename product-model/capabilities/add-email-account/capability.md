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

# Add email account

Connect a mailbox from a supported service; its credentials are checked before it is saved, and its inbox feeds leads.
