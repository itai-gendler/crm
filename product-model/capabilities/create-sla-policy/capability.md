---
availability:
- place: 'crm-web::administration'
domain: sla-policies
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_service_level_agreement/crm_service_level_agreement.py
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Sla/SlaPolicyView.vue
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Sla/SlaPolicyList.vue
---

# Create SLA policy

Add an SLA policy for leads or deals, with the first response time per communication status, working hours, holidays, conditions and validity; or duplicate one.
