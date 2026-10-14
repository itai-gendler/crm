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
---

# Move hierarchy member

Change whom someone reports to in the sales hierarchy, or move them to the top level.
