---
availability:
- place: 'crm-web::sales-workspace'
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_task/crm_task.py
- kind: code
  role: implementation
  target: frontend/src/pages/Tasks.vue
- kind: code
  role: implementation
  target: frontend/src/components/Activities/AllModals.vue
- kind: code
  role: implementation
  target: crm/api/todo.py
---

# Create task

Create a task on a lead or deal, on its own from Tasks, or from a call; the person it is assigned to is notified.
