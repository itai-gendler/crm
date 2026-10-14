---
availability:
- place: 'crm-web::sales-workspace'
domain: contacts
references:
- kind: code
  role: implementation
  target: frontend/src/pages/Contact.vue
- kind: code
  role: implementation
  target: crm/api/doc.py
---

# Delete contact

Delete a contact, taking them off the deals they were on.
