---
appliesTo:
- type: entity
  id: sla-policy
- type: entity
  id: lead
  facts:
  - Response by
  - First response time
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_service_level_agreement/crm_service_level_agreement.py
---

# SLA deadlines count only working hours

Response deadlines and response times count only the policy's working days and hours and skip the days in its holiday list.
