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

# Edit assignment rule

Change an assignment rule's condition, routing, assignees, days or priority.
