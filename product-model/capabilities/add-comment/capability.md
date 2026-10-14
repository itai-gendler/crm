---
availability:
- place: 'crm-web::sales-workspace'
references:
- kind: code
  role: implementation
  target: crm/api/comment.py
- kind: code
  role: implementation
  target: frontend/src/components/CommunicationArea.vue
---

# Add comment

Write an internal comment on a lead or deal, with files and @mentions; mentioned teammates are notified.
