---
availability:
- place: 'crm-web::sales-workspace'
domain: notifications
references:
- kind: code
  role: implementation
  target: frontend/src/components/Notifications.vue
- kind: code
  role: implementation
  target: crm/api/notifications.py
---

# Browse notifications

See one's latest notifications and open the lead or deal one is about, which marks it read.
