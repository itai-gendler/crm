---
availability:
- place: 'crm-web::invitation'
domain: invitations
references:
- kind: code
  role: implementation
  target: 'crm/api/__init__.py#accept_invitation'
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_invitation/crm_invitation.py
---

# Accept invitation

Follow an invitation link to join the CRM with the invited role.
