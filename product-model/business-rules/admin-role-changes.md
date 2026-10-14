---
appliesTo:
- type: entity
  id: crm-user
  effect: changes
  from: Admin
  contexts:
  - place: 'crm-web::administration'
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crm/api/user.py
---

# Only an Admin changes an Admin's role

A Manager cannot change or remove an Admin.
