---
availability:
- place: 'crm-web::sales-workspace'
references:
- kind: code
  role: implementation
  target: frontend/src/pages/CallLogs.vue
- kind: code
  role: implementation
  target: frontend/src/components/Modals/CallLogDetailModal.vue
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_call_log/crm_call_log.py
---

# Browse call logs

See every call log one may see, and open one with its notes, tasks and recording.
