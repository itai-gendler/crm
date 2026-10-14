---
appliesTo:
- type: entity
  id: assignment-rule
  effect: changes
  to: Enabled
permits:
- actors:
  - manager
  - admin
  when:
  - fact: Assignees
    present: true
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/AssignmentRules/AssignmentRuleListItem.vue
---

# An assignment rule is enabled only with assignees

Switching on a rule without assignees is refused.
