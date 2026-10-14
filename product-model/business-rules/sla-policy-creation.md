---
appliesTo:
- type: entity
  id: sla-policy
  effect: creates
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_service_level_agreement/crm_service_level_agreement.json
---

# Managers and Admins create SLA policies

SLA policies are open only to Managers and Admins.
