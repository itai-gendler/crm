---
appliesTo:
- type: entity
  id: deal
  effect: creates
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
---

# A new deal starts in Qualification

A deal created without a status is Qualification, or the first Open-type status when Qualification does not exist. Creating a deal with a person's details reuses a contact with the same email or mobile number, and an organization with the same name, instead of creating new ones.
