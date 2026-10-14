---
availability:
- place: 'crm-web::sales-workspace'
domain: deals
references:
- kind: code
  role: implementation
  target: frontend/src/components/DeleteLinkedDocModal.vue
- kind: code
  role: implementation
  target: crm/api/doc.py
---

# Delete deal

Delete a deal, deciding what happens to its linked notes, tasks and call logs.
