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

# Add deal contact

Add an existing contact to a deal's contacts. A deal's only contact is its primary contact.
