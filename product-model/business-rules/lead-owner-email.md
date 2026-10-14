---
appliesTo:
- type: entity
  id: lead
  facts:
  - Email
  - Lead owner
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.py
---

# A lead's email is never its owner's

A lead whose email address equals the lead owner's is refused.
