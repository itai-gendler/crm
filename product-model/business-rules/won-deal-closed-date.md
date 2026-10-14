---
appliesTo:
- type: entity
  id: deal
  effect: changes
  to: Won
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
---

# A won deal records its closed date

Moving a deal to a status of the Won type sets its closed date to today.
