---
availability:
- place: 'crm-web::sales-workspace'
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_view_settings/crm_view_settings.py
- kind: code
  role: implementation
  target: frontend/src/components/ViewControls.vue
---

# Create view

Save the current filters, sort, columns and layout of a list as a named view, or duplicate an existing one. A new view is private to its creator.
