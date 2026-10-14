---
availability:
- place: 'crm-web::sales-workspace'
- place: email-inbox
domain: leads
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.py
- kind: code
  role: implementation
  target: frontend/src/components/Modals/LeadModal.vue
- kind: code
  role: implementation
  target: crm/utils/__init__.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_call_log/crm_call_log.py
---

# Create lead

Add a lead: a salesperson from Leads or from a call with an unknown number, or a prospect by emailing an account that creates leads. The new lead gets its default status, its owner as assignee, an SLA policy when one applies, and may be assigned by an assignment rule.
