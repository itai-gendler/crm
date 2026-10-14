---
appliesTo:
- type: entity
  id: invitation
  effect: changes
  to: Expired
permits:
- unattended: true
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_invitation/crm_invitation.py
- kind: code
  role: implementation
  target: crm/hooks.py
---

# An invitation expires after three days

A pending invitation older than three days is expired by the daily run; an expired invitation's link no longer works.
