---
availability:
- place: 'crm-web::sales-workspace'
- place: email-inbox
references:
- kind: code
  role: implementation
  target: frontend/src/components/Activities/EmailArea.vue
- kind: code
  role: implementation
  target: crm/utils/__init__.py
---

# Reply to email

Answer an email on a lead or deal: a salesperson with Reply or Reply All from the record's timeline, or a prospect replying in their own mailbox, which lands on the same record.
