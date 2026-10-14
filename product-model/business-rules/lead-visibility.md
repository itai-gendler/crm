---
appliesTo:
- type: entity
  id: lead
  effect: reads
  contexts:
  - place: 'crm-web::sales-workspace'
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

# Owners, assignees, their hierarchy managers and unrestricted Managers and Admins read a lead

A Sales User reaches the leads they own or are assigned, whether or not the sales hierarchy is on. A Manager reaches every lead while the sales hierarchy is off or while they hold no place in it; a Manager in the hierarchy reaches the leads owned by or assigned to themselves or anyone below them in the tree. An Admin reaches every lead. A cancelled assignment gives no access.
