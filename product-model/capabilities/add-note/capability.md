---
availability:
- place: 'crm-web::sales-workspace'
references:
- kind: code
  role: implementation
  target: frontend/src/components/Activities/AllModals.vue
- kind: code
  role: implementation
  target: crm/fcrm/doctype/fcrm_note/fcrm_note.py
- kind: code
  role: implementation
  target: crm/integrations/api.py
---

# Add note

Write a note on a lead or deal, on its own from Notes, or about a call; mentioned teammates are notified.
