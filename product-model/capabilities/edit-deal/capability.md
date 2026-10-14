---
availability:
- place: 'crm-web::sales-workspace'
domain: deals
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
- kind: code
  role: implementation
  target: frontend/src/pages/Deal.vue
---

# Edit deal

Change a deal's details from its side panel or Data tab: organization, value, expected value and closure date, probability, products, next step and owner.
