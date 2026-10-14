---
appliesTo:
- type: entity
  id: lead
  facts:
  - Communication status
  - First responded on
  - First response time
  - SLA status
- type: entity
  id: sla-policy
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_service_level_agreement/crm_service_level_agreement.py
---

# Leaving the default priority records the first response

When a record's communication status changes away from its policy's default priority, its first response is recorded with its working time, and the SLA is Fulfilled when that was before the deadline and Failed otherwise. With rolling responses on, every later response is timed against a new deadline in the same way.
