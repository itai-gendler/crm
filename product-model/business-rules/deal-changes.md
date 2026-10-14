---
appliesTo:
- type: entity
  id: deal
  effect: changes
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

# Only those who may read a deal change it

Editing, assigning, moving and every other change to a deal is open to exactly the people who may read it. A Sales User reaches the deals they own or are assigned, whether or not the sales hierarchy is on. A Manager reaches every deal while the sales hierarchy is off or while they hold no place in it; a Manager in the hierarchy reaches the deals owned by or assigned to themselves or anyone below them in the tree. An Admin reaches every deal. A cancelled assignment gives no access.
