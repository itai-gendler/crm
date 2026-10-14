---
kind: primary
routes:
  main: Invitation
steps:
- text: The Invitee follows the invitation link
  kind: actor
  actor: invitee
  entities:
  - entity: invitation
    effect: reads
    facts:
    - Email
    - Role
  contexts:
    main:
      place: 'crm-web::invitation'
- text: 'The Product creates the person''s account with the invited role and accepts the invitation'
  kind: product
  actor: invitee
  entities:
  - entity: crm-user
    effect: creates
    to: Sales User
    facts:
    - Full name
    - Email
  - entity: invitation
    effect: changes
    from: Pending
    to: Accepted
    facts:
    - Accepted at
  contexts:
    main:
      place: 'crm-web::invitation'
- text: 'The Product sends the Invitee to set a password, after which the CRM opens'
  kind: product
  actor: invitee
  entities: []
  contexts:
    main:
      place: 'crm-web::invitation'
---

# Accept an invitation without a site account

## Trigger

A person invited as a Sales User opens the link in their email.

## Outcome

The person has an account with the Sales User role and sets their password to enter the CRM.
