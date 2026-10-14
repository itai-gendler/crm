---
availability:
- place: 'crm-web::sales-workspace'
domain: contacts
references:
- kind: code
  role: implementation
  target: frontend/src/pages/Contacts.vue
- kind: code
  role: implementation
  target: crm/overrides/contact.py
---

# Browse contacts

See every contact in the chosen view.
