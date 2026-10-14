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
  target: crm/api/contact.py
---

# Edit contact

Change a contact's details: name, organization, picture, and their email addresses and phone numbers, including which are primary.
