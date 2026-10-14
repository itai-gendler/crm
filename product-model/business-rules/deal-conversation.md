---
appliesTo:
- type: entity
  id: whatsapp-message
- type: entity
  id: deal
  facts:
  - Lead
references:
- kind: code
  role: implementation
  target: crm/api/whatsapp.py
---

# A deal's WhatsApp conversation includes its lead's

The WhatsApp tab of a deal shows the messages of the lead it was converted from as well as its own.
