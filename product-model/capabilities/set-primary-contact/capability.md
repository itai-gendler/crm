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

# Set primary contact

Make one of a deal's contacts its primary contact, whose email and mobile the deal uses.
