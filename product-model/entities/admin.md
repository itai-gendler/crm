---
kind: person
acts: external
relations:
- entity: crm-user
  verb: signs in as
  cardinality: one-to-one
- entity: lead
  verb: owns
  cardinality: one-to-many
- entity: lead
  verb: is assigned to
  cardinality: many-to-many
- entity: deal
  verb: owns
  cardinality: one-to-many
- entity: deal
  verb: is assigned to
  cardinality: many-to-many
- entity: comment
  verb: writes
  cardinality: one-to-many
- entity: view
  verb: owns
  cardinality: one-to-many
- entity: notification
  verb: receives
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crm/api/user.py
- kind: code
  role: implementation
  target: frontend/src/stores/users.js
---

# Admin

A person with the System Manager role, shown as Admin, or the site's Administrator. Admins see every lead and deal, and alone give the Manager and Admin roles and edit the sales hierarchy.
