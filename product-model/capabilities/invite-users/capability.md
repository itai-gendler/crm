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

# Invite users

Email invitations to join the CRM with a role; addresses that already belong to a user or an invitation are skipped.
