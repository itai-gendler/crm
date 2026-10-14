---
appliesTo:
- type: entity
  id: sla-policy
- type: entity
  id: lead
  facts:
  - SLA
- type: entity
  id: deal
  facts:
  - SLA
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_service_level_agreement/utils.py
---

# A lead or deal gets the first enabled, current, matching policy

A record without an SLA policy gets one when created or saved: an enabled policy for its type, within its start and end dates, that lists the record's communication status among its priorities and whose conditions it meets. The default policy is tried last. A record keeps its policy once it has one, even if the policy is later disabled.
