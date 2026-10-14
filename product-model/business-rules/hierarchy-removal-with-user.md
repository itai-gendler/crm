---
appliesTo:
- type: entity
  id: hierarchy-entry
  effect: removes
  contexts:
  - place: 'crm-web::administration::users'
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: 'crm/api/user.py#remove_crm_roles_from_user'
---

# Removing a person from the CRM takes them out of the sales hierarchy

When a Manager or Admin removes someone's CRM roles, that person's place in the sales hierarchy goes too.
