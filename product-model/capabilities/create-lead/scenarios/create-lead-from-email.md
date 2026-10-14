---
kind: primary
routes:
  main: Email inbox
steps:
- text: The Prospect emails an address whose account creates leads from incoming emails
  kind: actor
  actor: prospect
  entities:
  - entity: email-message
    effect: creates
    facts:
    - From
    - Subject
    - Content
    - Direction
    - Sent at
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: email-inbox
- text: 'No lead has the sender''s address'
  kind: condition
  entities:
  - entity: lead
    effect: reads
    facts:
    - Email
  contexts:
    main:
      place: email-inbox
- text: 'The Product creates a lead with the sender''s address and name, from source Email, and links the email to it'
  kind: product
  entities:
  - entity: lead
    effect: creates
    to: Open
    facts:
    - Email
    - First name
    - Last name
    - Source
    - Status
    - Communication status
  - entity: email-message
    effect: changes
    facts:
    - Linked to
  contexts:
    main:
      place: email-inbox
---

# Start a lead by emailing the business

## Trigger

An email from someone the CRM does not know arrives in an account with Create Lead from Incoming Emails on.

## Outcome

A new lead holds the sender's address and name, and the email is on its timeline.
