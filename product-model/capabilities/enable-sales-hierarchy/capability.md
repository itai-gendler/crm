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
  target: crm/permissions/org_hierarchy.py
---

# Enable sales hierarchy

Turn on the sales hierarchy so that Managers in the tree see their team's leads and deals instead of all of them.
