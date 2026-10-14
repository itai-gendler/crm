---
appliesTo:
- type: entity
  id: notification
  effect: changes
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
references:
- kind: code
  role: implementation
  target: crm/api/notifications.py
---

# Only its recipient marks a notification read

Marking as read touches only the person's own unread notifications.
