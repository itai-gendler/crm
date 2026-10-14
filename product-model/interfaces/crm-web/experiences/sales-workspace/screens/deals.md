---
entities:
- entity: deal
  shows:
  - Organization
  - Deal value
  - Status
  - Primary email
  - Primary mobile no
  - Assigned to
  - SLA status
  - Expected closure date
  - Expected deal value
  collects:
  - Organization
  - Status
  - Deal owner
  - Deal value
  - Expected deal value
  - Expected closure date
  - Contacts
  - Primary email
  - Primary mobile no
- entity: organization
  shows:
  - Organization name
  - Website
  - Territory
  - Industry
  - Annual revenue
  - No. of employees
- entity: contact
  shows:
  - First name
  - Last name
  - Email addresses
  - Phone numbers
  - Organization
- entity: view
  collects:
  - Label
  - Icon
  - View type
  - List
  - Filters
  - Sort
  - Columns
  - Pinned
  - Public
  - Default
entryPoints:
- crm-web: /crm/deals
---

# Deals

The deals the person may see, as a list, a kanban board by status or a grouped list, in the chosen view.
