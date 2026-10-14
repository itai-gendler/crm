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

# Add hierarchy members

Place Managers and Sales Users in the sales hierarchy, at the top or under someone.
