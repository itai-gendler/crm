---
entities:
- entity: organization
  shows:
  - Exchange rate
  - Organization name
  collects:
  - Territory
  - Address
- entity: contact
  collects:
  - Organization
- entity: deal
  collects:
  - Organization
  - Status
  - Deal owner
  - Deal value
  - Expected deal value
  - Expected closure date
entryPoints:
- crm-web: '/crm/organizations/:organizationId'
---

# Organization

One organization with its deals and contacts.
