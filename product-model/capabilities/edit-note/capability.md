---
availability:
- place: 'crm-web::sales-workspace'
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/fcrm_note/fcrm_note.py
- kind: code
  role: implementation
  target: frontend/src/components/Activities/NoteArea.vue
---

# Edit note

Change a note's title or content; only people newly mentioned are notified.
