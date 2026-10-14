---
appliesTo:
- type: entity
  id: deal
- type: entity
  id: crm-settings
  facts:
  - Forecasting
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
---

# With forecasting on, every deal has an expected value and closure date

While Forecasting is on, a deal without an expected deal value or an expected closure date is refused on every save.
