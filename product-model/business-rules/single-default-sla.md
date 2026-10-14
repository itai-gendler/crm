---
appliesTo:
- type: entity
  id: sla-policy
  facts:
  - Default
  - Apply on
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_service_level_agreement/crm_service_level_agreement.py
---

# Each record type has at most one default SLA policy

A second default policy for leads, or for deals, is refused.
