---
availability:
- place: 'crm-web::administration'
domain: users
references:
- kind: code
  role: implementation
  target: crm/api/user.py
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Users.vue
---

# Change user role

Make a CRM user a Sales User, Manager or Admin.
