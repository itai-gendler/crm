---
appliesTo:
- type: entity
  id: note
  facts:
  - Pinned
  - Pinned by
  - Pinned on
references:
- kind: code
  role: implementation
  target: 'crm/fcrm/doctype/fcrm_note/fcrm_note.py#set_pinned'
---

# Pinning a note does not change when it was last edited

Pinning and unpinning record who did it and when, and appear on the record's timeline, without marking the note as edited.
