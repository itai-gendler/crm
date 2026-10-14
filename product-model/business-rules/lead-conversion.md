---
appliesTo:
- type: entity
  id: lead
  effect: changes
  to: Won
  facts:
  - Converted
- type: entity
  id: deal
  effect: creates
- type: entity
  id: contact
  effect: creates
- type: entity
  id: organization
  effect: creates
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.py
- kind: code
  role: implementation
  target: frontend/src/pages/Leads.vue
---

# Converting a lead carries it into its deal

The deal takes every lead field it shares, including custom fields with the same label and type, the lead owner as deal owner and the lead's other assignees. The lead's person becomes a contact unless a contact with the same email exists, and its organization one unless an organization with that name exists. The lead becomes Qualified, where that status exists, and converted; converted leads no longer show in Leads.
