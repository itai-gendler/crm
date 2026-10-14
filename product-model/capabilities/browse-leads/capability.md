---
availability:
- place: 'crm-web::sales-workspace'
domain: leads
references:
- kind: code
  role: implementation
  target: frontend/src/pages/Leads.vue
- kind: code
  role: implementation
  target: crm/api/doc.py
- kind: code
  role: implementation
  target: crm/permissions/org_hierarchy.py
---

# Browse leads

See the leads one may see that have not been converted, as a list, a kanban board by status or a list grouped by a field, with filters, sorting, quick filters and the columns of the chosen view.
