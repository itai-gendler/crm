---
entities:
- entity: call-log
  shows:
  - From
  - Linked to
  - Caller
  - Receiver
  - Type
  - Status
  - Duration
  - To
  - Recording
  - Call notes
  - Call tasks
  collects:
  - Call notes
  - Call tasks
- entity: lead
  shows:
  - First name
  - Mobile no.
  - Lead owner
  - Status
  - Communication status
- entity: deal
  shows:
  - Organization
- entity: note
  collects:
  - Title
  - Content
  - Linked to
- entity: task
  collects:
  - Title
  - Priority
  - Linked to
entryPoints:
- crm-web: /crm/call-logs
---

# Call Logs

Every call log the person may see, and one call's details with its notes and tasks.
