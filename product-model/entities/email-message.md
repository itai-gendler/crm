---
references:
- kind: code
  role: implementation
  target: frontend/src/components/CommunicationArea.vue
- kind: code
  role: implementation
  target: crm/utils/__init__.py
---

# Email message

An email sent to or received from a prospect, kept on the lead or deal it belongs to.

## Information kept

- **Subject** — the subject
- **Content** — the body
- **From** — the sender
- **To** — the recipients
- **CC** — copied recipients
- **BCC** — blind-copied recipients
- **Attachments** — attached files
- **Direction** — Sent or Received
- **Linked to** — the lead or deal it belongs to
- **Sent at** — when it was sent or received
