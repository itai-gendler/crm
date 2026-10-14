---
references:
- kind: code
  role: implementation
  target: frontend/src/components/Activities/AttachmentArea.vue
- kind: code
  role: implementation
  target: crm/api/__init__.py
---

# Attachment

A file uploaded to a lead or deal.

## Information kept

- **File** — the file
- **Private** — whether only signed-in people may open it
- **Linked to** — the lead or deal it belongs to
