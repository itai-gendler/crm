---
availability:
- place: 'crm-web::sales-workspace'
domain: leads
references:
- kind: code
  role: implementation
  target: crm/api/todo.py
- kind: code
  role: implementation
  target: frontend/src/components/AssignTo.vue
- kind: code
  role: implementation
  target: frontend/src/components/ListBulkActions.vue
---

# Assign lead

Add people to a lead's assignees from its page or for several leads at once from Leads. The latest assignee becomes the lead owner and is notified.
