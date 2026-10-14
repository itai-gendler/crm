---
availability:
- place: 'crm-web::sales-workspace'
domain: deals
references:
- kind: code
  role: implementation
  target: crm/api/todo.py
- kind: code
  role: implementation
  target: frontend/src/components/AssignTo.vue
---

# Assign deal

Add people to a deal's assignees. The latest assignee becomes the deal owner and is notified.
