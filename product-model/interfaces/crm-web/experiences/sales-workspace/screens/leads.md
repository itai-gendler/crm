---
entities:
- entity: lead
  shows:
  - Full name
  - Organization
  - Status
  - Email
  - Mobile no.
  - Assigned to
  - SLA status
  - First response time
  - Lead owner
  - First name
  collects:
  - First name
  - Last name
  - Email
  - Mobile no.
  - Organization
  - Website
  - No. of employees
  - Status
  - Lead owner
  - Assigned to
- entity: view
  shows:
  - Label
  - Filters
  collects:
  - Label
  - View type
  - List
  - Filters
  - Sort
  - Columns
  - Kanban column
entryPoints:
- crm-web: /crm/leads
---

# Leads

The leads the person may see that have not been converted, as a list, a kanban board by status or a grouped list, in the chosen view.
