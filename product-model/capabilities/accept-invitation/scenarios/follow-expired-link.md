---
kind: validation
routes:
  main: Invitation
steps:
- text: The Invitee follows a link whose invitation has expired
  kind: actor
  actor: invitee
  entities:
  - entity: invitation
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::invitation'
- text: 'The Product refuses: Invalid or expired key'
  kind: condition
  actor: invitee
  entities:
  - entity: invitation
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::invitation'
---

# Follow an expired invitation link

## Trigger

A person opens an invitation link after it expired or was deleted.

## Outcome

No role is given; the person needs a new invitation.
