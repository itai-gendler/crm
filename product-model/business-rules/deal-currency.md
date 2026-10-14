---
appliesTo:
- type: entity
  id: deal
  facts:
  - Currency
  - Exchange rate
- type: entity
  id: organization
  facts:
  - Currency
  - Exchange rate
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
- kind: code
  role: implementation
  target: crm/api/exchange_rate.py
---

# Deal and organization figures convert to the CRM's currency

A deal or organization in another currency keeps an exchange rate to the CRM's currency, fetched when its currency changes.
