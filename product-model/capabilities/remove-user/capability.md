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

# Remove user

Take away a person's CRM roles and their place in the sales hierarchy.
