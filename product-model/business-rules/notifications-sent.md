---
appliesTo:
- type: entity
  id: notification
  effect: creates
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_notification/crm_notification.py
- kind: code
  role: implementation
  target: crm/api/comment.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/fcrm_note/fcrm_note.py
- kind: code
  role: implementation
  target: crm/api/todo.py
- kind: code
  role: implementation
  target: crm/api/whatsapp.py
---

# Mentions, assignments and incoming WhatsApp messages notify people

A mention in a comment or note on a lead or deal notifies the person mentioned, once per note; assigning or unassigning a lead, deal or task notifies the assignee; an incoming WhatsApp message notifies the record's assignees. Nobody is notified of their own action, and the same notice is never sent twice.
