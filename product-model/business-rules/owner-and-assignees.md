---
appliesTo:
- type: entity
  id: lead
  facts:
  - Lead owner
  - Assigned to
- type: entity
  id: deal
  facts:
  - Deal owner
  - Assigned to
references:
- kind: code
  role: implementation
  target: crm/api/todo.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
---

# A lead's or deal's owner is assigned, and the latest assignee owns it

Setting an owner assigns the record to them and shares it with them. Assigning someone makes them the owner; removing an assignee clears the owner. Assigning needs the right to change the record.
