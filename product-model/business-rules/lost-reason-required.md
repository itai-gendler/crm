---
appliesTo:
- type: entity
  id: lead
  effect: changes
  to: Lost
- type: entity
  id: deal
  effect: changes
  to: Lost
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/utils.py
---

# A lost lead or deal has a lost reason

Moving a lead or deal to a status of the Lost type needs a lost reason, and the reason Other needs lost notes. The lost reason section appears in the side panel while it is lost.
