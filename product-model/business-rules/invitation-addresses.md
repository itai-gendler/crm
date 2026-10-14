---
appliesTo:
- type: entity
  id: invitation
  effect: creates
references:
- kind: code
  role: implementation
  target: 'crm/api/__init__.py#invite_by_email'
---

# Addresses already known are not invited again

Inviting skips an address that already belongs to a user or to any invitation, and reports it.
