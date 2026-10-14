---
references:
- kind: code
  role: implementation
  target: crm/api/whatsapp.py
- kind: code
  role: implementation
  target: frontend/src/components/Activities/Activities.vue
---

# WhatsApp message

A WhatsApp message exchanged with a lead's or deal's mobile number.

## Information kept

- **Message** — the text or caption
- **Media** — an attached document, image or video
- **Template** — the approved WhatsApp template it was sent from
- **Direction** — Incoming or Outgoing
- **Phone number** — the prospect's number
- **Replying to** — the message it answers
- **Linked to** — the lead or deal it belongs to
