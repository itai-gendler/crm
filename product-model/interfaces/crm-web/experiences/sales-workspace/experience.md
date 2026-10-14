---
actors:
- sales-user
- manager
- admin
access: authenticated
entryPoints:
- crm-web: /crm/leads
references:
- kind: code
  role: implementation
  target: frontend/src/router.js
- kind: code
  role: implementation
  target: frontend/src/utils/navigation.js
---

# Sales workspace

Where everyone with a CRM role works: the Leads, Deals, Contacts, Organizations, Notes, Tasks and Call Logs lists, each record's page, notifications, and the parts of Settings open to every role.
