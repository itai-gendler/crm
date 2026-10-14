---
appliesTo:
- type: entity
  id: lead
- type: entity
  id: deal
- type: entity
  id: activity
references:
- kind: code
  role: implementation
  target: crm/api/activities.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_status_change_log/crm_status_change_log.py
---

# Changes to a lead or deal are recorded in its activity

Creation, field and status changes, assignments, emails, comments, calls, notes and attachments appear in the record's Activity tab with who did them and when. A deal's activity includes that of the lead it came from, when the person may read the lead. Status changes also record how long the record spent in the previous status.
