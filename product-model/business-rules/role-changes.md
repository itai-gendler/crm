---
appliesTo:
- type: entity
  id: crm-user
  effect: changes
  contexts:
  - place: 'crm-web::administration'
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crm/api/user.py
---

# Managers and Admins change people's CRM roles

Adding people, changing their role and removing them are open to Managers and Admins.
