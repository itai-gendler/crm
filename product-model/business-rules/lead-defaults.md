---
appliesTo:
- type: entity
  id: lead
  effect: creates
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.py
- kind: code
  role: implementation
  target: frontend/src/components/Modals/LeadModal.vue
---

# A new lead starts in New, named and owned

A lead created without a status is New, or the first Open-type status when New does not exist. Its full name is built from its salutation and names; without a first name it takes the organization's name, else the part of the email before @. A lead needs a person's or an organization's name. In the CRM its owner defaults to the person creating it.
