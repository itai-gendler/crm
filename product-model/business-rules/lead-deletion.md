---
appliesTo:
- type: entity
  id: lead
  effect: removes
permits:
- actors:
  - admin
- actors:
  - manager
  when:
  - entity: crm-settings
    fact: Sales hierarchy
    is: 'Off'
- actors:
  - manager
  when:
  - entity: manager
    fact: In sales hierarchy
    is: 'No'
- related:
  - verb: owns
    entity: manager
- related:
  - verb: is assigned to
    entity: manager
- related:
  - verb: owns
    entity: sales-user
- related:
  - verb: is assigned to
    entity: sales-user
references:
- kind: code
  role: implementation
  target: crm/permissions/org_hierarchy.py
- kind: code
  role: implementation
  target: crm/hooks.py
- kind: code
  role: implementation
  target: crm/permissions/test_org_hierarchy.py
---

# Only those who may read a lead delete it

Deleting a lead is open to exactly the people who may read it.
