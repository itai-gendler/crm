---
type: messaging
actors:
- prospect
references:
- kind: code
  role: implementation
  target: crm/api/whatsapp.py
- kind: code
  role: implementation
  target: crm/hooks.py
---

# WhatsApp

The business's WhatsApp number, connected through a separately installed WhatsApp app. A prospect's messages land on the lead or deal with their mobile number.
