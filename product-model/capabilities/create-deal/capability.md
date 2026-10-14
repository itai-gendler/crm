---
availability:
- place: 'crm-web::sales-workspace'
domain: deals
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
- kind: code
  role: implementation
  target: frontend/src/components/Modals/DealModal.vue
---

# Create deal

Add a deal from Deals, a contact's page or an organization's page, with an existing or new contact and organization.
