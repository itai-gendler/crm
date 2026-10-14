---
availability:
- place: 'crm-web::sales-workspace'
domain: organizations
references:
- kind: code
  role: implementation
  target: frontend/src/components/Modals/OrganizationModal.vue
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_organization/crm_organization.py
---

# Create organization

Add an organization from Organizations or while picking one elsewhere.
