---
availability:
- place: 'crm-web::sales-workspace'
references:
- kind: code
  role: implementation
  target: 'crm/fcrm/doctype/fcrm_note/fcrm_note.py#set_pinned'
- kind: code
  role: implementation
  target: frontend/src/components/Activities/NoteArea.vue
---

# Pin note

Pin a note to the top of its record's notes, without changing when it was last edited.
