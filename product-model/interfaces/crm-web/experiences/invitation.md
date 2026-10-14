---
actors:
- invitee
access: public
entryPoints:
- crm-web: '/api/method/crm.api.accept_invitation?key=:key'
references:
- kind: code
  role: implementation
  target: crm/api/__init__.py
---

# Invitation

The link an invitation email carries, which a person follows before they can sign in.
