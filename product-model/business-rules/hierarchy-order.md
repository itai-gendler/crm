---
appliesTo:
- type: entity
  id: hierarchy-entry
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Hierarchy/useDragDrop.js
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_sales_hierarchy/crm_sales_hierarchy.py
---

# Managers sit above Sales Users in the sales hierarchy

Only Managers and Sales Users have a place in the tree, each at most once. A Manager reports to a Manager; a Sales User reports to a Manager or a Sales User; nobody reports to someone below themselves.
