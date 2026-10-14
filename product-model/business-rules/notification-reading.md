---
appliesTo:
- type: entity
  id: notification
  effect: reads
permits:
- related:
  - verb: receives
    entity: sales-user
- related:
  - verb: receives
    entity: manager
- related:
  - verb: receives
    entity: admin
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_notification/crm_notification.py
---

# Only its recipient reads a notification

A person sees and marks only their own notifications; Admins may read any.
