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
  target: crm/permissions/org_hierarchy.py
- kind: code
  role: implementation
  target: frontend/src/stores/users.js
---

# Manager

A person with the Sales Manager role, shown as Manager. Managers see the whole pipeline unless the sales hierarchy limits them to their team, and look after the CRM's users, rules and policies in Settings.

## Information kept

- **In sales hierarchy** — whether the Manager holds a place in the sales hierarchy
