---
type: web
actors:
- sales-user
- manager
- admin
- invitee
entryPoints:
- web: /crm
references:
- kind: code
  role: implementation
  target: frontend/src/router.js
- kind: code
  role: implementation
  target: crm/hooks.py
- kind: code
  role: implementation
  target: crm/www/crm.py
---

# CRM web app

The single-page web app served under `/crm`, where the sales team works leads, deals, contacts, organizations, notes, tasks and calls, and where Managers and Admins look after the CRM in Settings. People sign in through the site's login page; a signed-in person without a CRM role is shown Not Permitted. The page an emailed invitation link opens is part of it.
