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
  target: frontend/src/components/Modals/ConvertToDealModal.vue
---

# Convert lead

Turn a lead into a deal: the lead's organization and person become an organization and a contact (or existing ones are chosen), a deal carries the lead's details, owner, assignees and SLA, and the lead is marked converted.
