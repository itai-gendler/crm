---
appliesTo:
- type: entity
  id: view
  effect: changes
  facts:
  - Default
permits:
- actors:
  - sales-user
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_view_settings/crm_view_settings.py
---

# Everyone chooses their own default view, one per list

Anyone sets which view opens first for them; setting one clears their other default for the same list.
