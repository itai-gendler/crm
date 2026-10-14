---
appliesTo:
- type: entity
  id: lead
  facts:
  - Mobile no.
- type: entity
  id: deal
  facts:
  - Primary mobile no
- type: entity
  id: whatsapp-message
references:
- kind: code
  role: implementation
  target: crm/api/whatsapp.py
---

# Moving a record off a number it has WhatsApp messages with needs confirmation

Changing a lead's or deal's mobile number away from one it has a WhatsApp conversation with is refused until the person confirms, because replies from the old number stop showing on the record. Imports and upgrades need no confirmation.
