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
  target: frontend/src/components/Modals/LostReasonModal.vue
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_status_change_log/crm_status_change_log.py
---

# Change lead status

Set a lead's status from its page, the kanban board or a bulk edit. Moving it to a Lost status asks for a lost reason.
