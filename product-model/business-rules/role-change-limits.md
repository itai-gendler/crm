---
appliesTo:
- type: entity
  id: crm-user
  effect: changes
references:
- kind: code
  role: implementation
  target: crm/api/user.py
---

# Nobody removes themselves, and hierarchy heads stay Managers

A person cannot remove their own CRM roles. Someone with direct reports in the sales hierarchy, or at its top level, cannot be made a Sales User until they are out of the tree. People whose roles a role profile governs are refused, because the profile would undo the change. Removing a person also takes them out of the sales hierarchy; a Sales User is limited to the CRM's module.
