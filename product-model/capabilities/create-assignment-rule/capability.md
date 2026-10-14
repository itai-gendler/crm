---
availability:
- place: 'crm-web::administration'
domain: assignment-rules
references:
- kind: code
  role: implementation
  target: crm/api/assignment_rule.py
- kind: code
  role: implementation
  target: frontend/src/components/Settings/AssignmentRules/AssignmentRuleView.vue
- kind: code
  role: implementation
  target: frontend/src/components/Settings/AssignmentRules/AssignmentRuleListItem.vue
- kind: code
  role: implementation
  target: frontend/src/components/Settings/AssignmentRules/AssigneeRules.vue
---

# Create assignment rule

Add a rule that assigns new leads or deals matching its condition to its assignees, by rotation or by workload, on chosen days; or duplicate one.
