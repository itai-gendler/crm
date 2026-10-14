---
appliesTo:
- type: entity
  id: crm-user
  effect: changes
  to: Manager
  contexts:
  - place: 'crm-web::administration'
- type: entity
  id: crm-user
  effect: changes
  to: Admin
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

# Only an Admin gives the Manager or Admin role

Making someone a Manager or an Admin, whether adding them or changing their role, is an Admin's.
