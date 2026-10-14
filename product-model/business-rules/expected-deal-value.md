---
appliesTo:
- type: entity
  id: deal
  facts:
  - Expected deal value
  - Net total
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
---

# A deal's expected value follows its products

While Auto update Expected Deal Value is on, a deal that already has an expected deal value takes its products' net total as the expected deal value when saved.
