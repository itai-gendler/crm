---
entities:
- entity: lead
  shows:
  - Status
  - Converted
- entity: deal
  shows:
  - Probability
  - Assigned to
  - Communication status
  - SLA
  - SLA status
  - Response by
  - Net total
  - Expected deal value
  - Status
  - Closed date
  - Primary email
  - Primary mobile no
  - Deal owner
  collects:
  - Products
  - Expected closure date
  - Next step
  - Status
  - Lost reason
  - Contacts
  - Assigned to
- entity: contact
  shows:
  - Full name
- entity: note
  collects:
  - Linked to
  - Content
- entity: email-message
  shows:
  - Subject
  - From
  - To
  - CC
  - Content
  collects:
  - Subject
  - Content
  - From
  - To
  - CC
  - Direction
  - Linked to
  - Sent at
- entity: comment
  collects:
  - Content
  - Author
  - Mentions
  - Linked to
- entity: whatsapp-message
  shows:
  - Message
  - Direction
  - Media
  collects:
  - Message
  - Direction
  - Phone number
  - Linked to
- entity: task
  collects:
  - Title
  - Priority
  - Due date
  - Assigned to
  - Linked to
- entity: attachment
  collects:
  - File
  - Private
  - Linked to
entryPoints:
- crm-web: '/crm/deals/:dealId'
---

# Deal

One deal: its organization, contacts, details and SLA in the side panel, its status and assignees, and its activity, emails, comments, data, calls, tasks, notes, attachments and WhatsApp conversation.
