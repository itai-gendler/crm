---
appliesTo:
- type: entity
  id: assignment-rule
- type: entity
  id: lead
  facts:
  - Assigned to
- type: entity
  id: deal
  facts:
  - Assigned to
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/AssignmentRules/AssigneeRules.vue
- kind: code
  role: implementation
  target: crm/api/assignment_rule.py
---

# Enabled assignment rules assign new leads and deals

An enabled rule assigns a lead or deal matching its assignment condition, on one of its assignment days, to one of its assignees: in turn with Auto-rotate, or to whoever has the fewest open assignments with Assign by workload. Rules are tried by priority.
