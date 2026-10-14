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

# Disable SLA policy

Turn an SLA policy off; the default policy cannot be turned off.
