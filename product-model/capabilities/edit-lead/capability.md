---
availability:
- place: 'crm-web::sales-workspace'
domain: leads
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.py
- kind: code
  role: implementation
  target: frontend/src/pages/Lead.vue
- kind: code
  role: implementation
  target: crm/api/whatsapp.py
---

# Edit lead

Change a lead's details from its side panel or Data tab: name, contact details, organization details, source, products and the lead owner.
