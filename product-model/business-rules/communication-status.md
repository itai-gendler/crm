---
appliesTo:
- type: entity
  id: lead
  facts:
  - Communication status
- type: entity
  id: deal
  facts:
  - Communication status
- type: entity
  id: crm-settings
  facts:
  - Mark lead/deal as replied on response
  - Reopen lead/deal on new communication
references:
- kind: code
  role: implementation
  target: crm/utils/__init__.py
---

# Emails set the communication status only when the settings say so

With Mark lead/deal as replied on response on, an email sent from a lead or deal sets its communication status to Replied; with Reopen lead/deal on new communication on, an email received sets it to Open. Only the record's latest email counts.
