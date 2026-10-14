---
kind: primary
routes:
  main: Invitation
steps:
- text: 'The Invitee, who already has a site account, follows the invitation link'
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
- text: 'The Product gives the account the invited role, accepts the invitation and signs the Invitee in to the CRM'
  kind: product
  actor: invitee
  entities:
  - entity: crm-user
    effect: changes
    from: Without CRM access
    to: Manager
    facts: []
  - entity: invitation
    effect: changes
    from: Pending
    to: Accepted
    facts:
    - Accepted at
  contexts:
    main:
      place: 'crm-web::invitation'
---

# Accept an invitation with an existing site account

## Trigger

A site user invited as a Manager opens the link.

## Outcome

The person is signed in to the CRM as a Manager.
