---
appliesTo:
- type: entity
  id: lead
  effect: changes
  from: Lost
  facts:
  - Converted
permits: []
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.py
- kind: code
  role: implementation
  target: frontend/src/pages/Lead.vue
---

# A lost lead is never converted

A lead whose status is of the Lost type cannot become a deal; the CRM offers no conversion and the server refuses it.
