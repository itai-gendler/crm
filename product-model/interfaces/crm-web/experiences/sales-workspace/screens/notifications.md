---
entities:
- entity: notification
  shows:
  - Type
  - From
  - Message
  - Read
  - Linked to
  collects:
  - Read
entryPoints:
- crm-web: /crm/notifications
---

# Notifications

The person's latest notifications, newest first.
