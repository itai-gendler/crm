---
appliesTo:
- type: entity
  id: view
  effect: removes
permits:
- related:
  - verb: owns
    entity: sales-user
- related:
  - verb: owns
    entity: manager
- related:
  - verb: owns
    entity: admin
- actors:
  - manager
  when:
  - fact: Public
    is: 'Yes'
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_view_settings/crm_view_settings.py
---

# A view's owner, a Manager for public views, and Admins delete a view

A private view is deleted only by its owner; a public view by Managers; any view by Admins.
