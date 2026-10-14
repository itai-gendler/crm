---
domain: notifications
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_notification/crm_notification.py
- kind: code
  role: implementation
  target: crm/api/notifications.py
---

# Notification

An in-app notice to one person: a mention, an assignment or an incoming WhatsApp message.

## Information kept

- **Type** — Mention, Assignment or WhatsApp
- **From** — who caused it
- **Message** — what it says
- **Read** — whether the person has read it
- **Linked to** — the lead or deal it opens
