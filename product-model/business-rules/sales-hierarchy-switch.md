---
appliesTo:
- type: entity
  id: crm-settings
  effect: changes
  facts:
  - Sales hierarchy
permits:
- actors:
  - admin
- actors:
  - manager
  when:
  - fact: Sales hierarchy
    is: 'Off'
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Hierarchy/Hierarchy.vue
- kind: code
  role: implementation
  target: docs/user-hierarchy.md
---

# Only an Admin turns the sales hierarchy off

Managers and Admins turn the sales hierarchy on; only an Admin turns it off. Turning it off keeps the tree.
