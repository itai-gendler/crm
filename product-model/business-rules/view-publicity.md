---
appliesTo:
- type: entity
  id: view
  effect: changes
  facts:
  - Public
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_view_settings/crm_view_settings.py
---

# Only Managers and Admins make views public or private

Making a view public unpins it and shares it with everyone; making it private gives it to the person who did so.
