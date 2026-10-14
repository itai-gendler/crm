---
appliesTo:
- type: entity
  id: invitation
  effect: creates
permits:
- actors:
  - admin
- actors:
  - manager
  when:
  - fact: Role
    is: Sales User
references:
- kind: code
  role: implementation
  target: 'crm/api/__init__.py#invite_by_email'
---

# A Manager invites only Sales Users

Admins invite people as Sales Users, Managers or Admins; Managers invite Sales Users only.
