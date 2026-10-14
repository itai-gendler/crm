---
appliesTo:
- type: entity
  id: invitation
  effect: removes
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_invitation/crm_invitation.json
---

# Managers and Admins delete invitations

Only Managers and Admins delete an invitation.
