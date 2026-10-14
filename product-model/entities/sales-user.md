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
  target: crm/api/__init__.py
- kind: code
  role: implementation
  target: crm/permissions/org_hierarchy.py
---

# Sales User

A salesperson with the Sales User role. A Sales User works the leads and deals they own or are assigned, with their notes, tasks, calls and conversations.
