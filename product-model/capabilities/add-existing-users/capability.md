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
- kind: code
  role: implementation
  target: frontend/src/components/Modals/AddExistingUserModal.vue
---

# Add existing users

Give people who already have a site account a CRM role.
