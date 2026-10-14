---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses New Email on the lead and picks an enabled email template for leads
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Email
  - entity: email-template
    effect: reads
    facts:
    - Name
    - Subject
    - Content
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Sales User adjusts the text, adds a CC and sends'
  kind: actor
  actor: sales-user
  entities:
  - entity: email-message
    effect: creates
    facts:
    - Subject
    - Content
    - From
    - To
    - CC
    - Attachments
    - Direction
    - Linked to
    - Sent at
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product sends it from the chosen address and shows it on the lead''s Emails tab and in its activity'
  kind: product
  actor: sales-user
  entities:
  - entity: email-message
    effect: reads
    facts:
    - Subject
    - To
    - Sent at
  - entity: activity
    effect: reads
    facts:
    - Actor
    - Change
    - Time
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Email a lead

## Trigger

A Sales User wants to write to a lead's person.

## Outcome

The email is sent and kept on the lead.

## Edge cases

- The person's email signature, or the default outgoing account's, starts the email

## Decision points

### Communication status

Is Mark lead/deal as replied on response on?

- On → the lead's communication status becomes Replied
- Off → it is left as it was
