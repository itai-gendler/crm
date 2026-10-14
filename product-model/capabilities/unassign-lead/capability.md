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
  target: crm/api/doc.py
---

# Unassign lead

Take someone off a lead's assignees, or clear all assignments from Leads. The lead loses its owner and the person is told.
