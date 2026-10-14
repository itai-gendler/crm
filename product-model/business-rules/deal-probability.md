---
appliesTo:
- type: entity
  id: deal
  facts:
  - Probability
  - Status
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
- kind: code
  role: implementation
  target: crm/install.py
---

# A deal's probability defaults to its status's

A deal with no probability takes the probability of its status: 10 for Qualification up to 100 for Won by default.
