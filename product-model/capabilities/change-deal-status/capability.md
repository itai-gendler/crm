---
availability:
- place: 'crm-web::sales-workspace'
domain: deals
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
- kind: code
  role: implementation
  target: frontend/src/pages/Deal.vue
- kind: code
  role: implementation
  target: frontend/src/components/Kanban/KanbanView.vue
---

# Change deal status

Move a deal along the pipeline from its page or the kanban board. Winning it records the closed date; losing it asks for a lost reason.
