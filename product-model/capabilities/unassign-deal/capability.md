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
  target: crm/api/doc.py
---

# Unassign deal

Take someone off a deal's assignees. The deal loses its owner and the person is told.
