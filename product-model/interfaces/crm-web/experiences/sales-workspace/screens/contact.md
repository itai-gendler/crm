---
entities:
- entity: contact
  shows:
  - Full name
  - Organization
  collects:
  - Email addresses
  - Phone numbers
- entity: deal
  shows:
  - Primary mobile no
  - Primary email
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
entryPoints:
- crm-web: '/crm/contacts/:contactId'
---

# Contact

One contact with their email addresses, phone numbers and the deals they take part in.
