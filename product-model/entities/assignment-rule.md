---
domain: assignment-rules
references:
- kind: code
  role: implementation
  target: crm/api/assignment_rule.py
- kind: code
  role: implementation
  target: frontend/src/components/Settings/AssignmentRules/AssignmentRuleView.vue
---

# Assignment rule

A rule that assigns new leads or deals to salespeople automatically.

## Information kept

- **Name** — its name
- **Description** — what it is for
- **Apply on** — Lead or Deal
- **Priority** — the order rules are tried in
- **Assignment condition** — which records it assigns
- **Unassignment condition** — when it takes an assignment back
- **Routing** — Auto-rotate or Assign by workload
- **Assignees** — the salespeople it assigns to
- **Assignment days** — the weekdays it is active
- **Last user** — who it assigned last

## States

### Enabled

Assigns matching records.

### Disabled

Assigns nothing.
