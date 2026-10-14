---
availability:
- place: 'crm-web::sales-workspace'
references:
- kind: code
  role: implementation
  target: frontend/src/components/SLASection.vue
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_service_level_agreement/crm_service_level_agreement.py
---

# Change communication status

Set whether a lead or deal is waiting on the sales team (Open) or has been answered (Replied) from its SLA section; answering records the response against its SLA policy.
