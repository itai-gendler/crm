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

# Make view private

Withdraw a public view, making it the withdrawing person's own.
