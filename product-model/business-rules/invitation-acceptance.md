---
appliesTo:
- type: entity
  id: invitation
  effect: changes
  to: Accepted
- type: entity
  id: crm-user
  effect: changes
  contexts:
  - place: 'crm-web::invitation'
permits:
- actors:
  - invitee
references:
- kind: code
  role: implementation
  target: 'crm/api/__init__.py#accept_invitation'
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_invitation/crm_invitation.py
---

# Only the invitee accepts an invitation, once, while it is pending

Following a pending invitation's link gives the person the invited role, with the roles below it, and accepts the invitation; the link stops working once used.
