---
type: messaging
actors:
- prospect
references:
- kind: code
  role: implementation
  target: crm/utils/__init__.py
- kind: code
  role: implementation
  target: crm/api/settings.py
---

# Email inbox

The mailboxes of the email accounts the CRM receives into. A prospect's reply to an email sent from a lead or deal joins that record; an email from an unknown sender can start a new lead.
