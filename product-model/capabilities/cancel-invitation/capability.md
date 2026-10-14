---
availability:
- place: 'crm-web::administration'
domain: invitations
references:
- kind: code
  role: implementation
  target: crm/api/__init__.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_invitation/crm_invitation.py
- kind: code
  role: implementation
  target: frontend/src/components/Settings/InviteUserPage.vue
---

# Cancel invitation

Delete a pending invitation.
