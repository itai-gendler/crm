---
entities:
- entity: lead
  shows:
  - Full name
  - Assigned to
  - Communication status
  - SLA
  - SLA status
  - Response by
  - Net total
  - Mobile no.
  - Status
  - Organization
  - Email
  - Lead owner
  - First responded on
  - First response time
  collects:
  - Job title
  - Territory
  - Products
  - Lead owner
  - Mobile no.
  - Status
  - Lost reason
  - Lost notes
  - Assigned to
  - Communication status
  - Converted
- entity: deal
  shows:
  - Organization
  - Contacts
  - Primary email
  - Primary mobile no
  - Deal owner
  - Assigned to
  - Status
  - Lead
  - Products
  - Net total
  - Website
  - Territory
  - Source
  - Communication status
  - SLA
  - SLA status
  - Response by
  collects:
  - Organization
  - Contacts
  - Deal owner
  - Status
  - Lead
- entity: organization
  shows:
  - Organization name
  - Website
  - Territory
  - Industry
  - Annual revenue
  - No. of employees
- entity: contact
  shows:
  - First name
  - Last name
  - Email addresses
  - Phone numbers
  - Organization
  - Designation
  - Full name
- entity: note
  shows:
  - Title
  collects:
  - Title
  - Content
  - Linked to
  - Pinned
  - Pinned by
  - Pinned on
- entity: task
  shows:
  - Title
- entity: email-template
  shows:
  - Name
  - Subject
  - Content
- entity: email-message
  shows:
  - Subject
  - To
  - Sent at
  collects:
  - Subject
  - Content
  - From
  - To
  - CC
  - Attachments
  - Direction
  - Linked to
  - Sent at
- entity: activity
  shows:
  - Actor
  - Change
  - Time
- entity: comment
  collects:
  - Content
- entity: call-log
  shows:
  - Type
  - Status
  - Caller
  - From
  - To
  - Medium
  - Start time
  - Linked to
  - Duration
  - Recording
  collects:
  - Type
  - Status
  - From
  - To
  - Duration
  - Linked to
  - Medium
entryPoints:
- crm-web: '/crm/leads/:leadId'
---

# Lead

One lead: its details and SLA in the side panel, its status and assignees, and its activity, emails, comments, data, calls, tasks, notes, attachments and WhatsApp conversation.
