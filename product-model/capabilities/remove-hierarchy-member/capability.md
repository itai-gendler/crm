---
availability:
- place: 'crm-web::administration'
domain: sales-hierarchy
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Hierarchy/Hierarchy.vue
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_sales_hierarchy/crm_sales_hierarchy.py
- kind: code
  role: implementation
  target: docs/user-hierarchy.md
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Hierarchy/useRemoveNode.js
---

# Remove hierarchy member

Take someone out of the sales hierarchy, deciding what happens to their direct reports; they keep their CRM role.
