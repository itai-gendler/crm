---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Manager enters email addresses, picks Sales User and chooses Send Invites'
  kind: actor
  actor: manager
  entities:
  - entity: invitation
    effect: creates
    to: Pending
    facts:
    - Email
    - Role
    - Invited by
    - Sent at
  - entity: sales-user
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::invite-user'
- text: The Product emails each person an invitation link
  kind: product
  actor: manager
  entities:
  - entity: invitation
    effect: reads
    facts:
    - Email
    - Sent at
  contexts:
    main:
      place: 'crm-web::administration::invite-user'
---

# Invite people as Sales Users

## Trigger

A Manager invites new salespeople.

## Outcome

Each new address has a pending invitation and an email with its link: Invitations sent successfully.

## Edge cases

- An address that already belongs to a user or already has an invitation is skipped and reported
