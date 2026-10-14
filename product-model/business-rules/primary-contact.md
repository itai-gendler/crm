---
appliesTo:
- type: entity
  id: deal
  facts:
  - Contacts
  - Primary email
  - Primary mobile no
- type: entity
  id: contact
  facts:
  - Email addresses
  - Phone numbers
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
- kind: code
  role: implementation
  target: crm/api/contact.py
---

# A deal has at most one primary contact and uses their email and mobile

A deal's only contact is its primary; more than one primary is refused. The deal's primary email and mobile number are the primary contact's, cleared when there is none, and follow the contact when the contact's own primary email or mobile changes.
