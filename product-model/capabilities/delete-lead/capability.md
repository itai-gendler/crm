---
availability:
- place: 'crm-web::sales-workspace'
domain: leads
references:
- kind: code
  role: implementation
  target: frontend/src/components/DeleteLinkedDocModal.vue
- kind: code
  role: implementation
  target: crm/api/doc.py
---

# Delete lead

Delete a lead, or several from Leads, deciding what happens to the notes, tasks and call logs linked to it.
