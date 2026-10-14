---
kind: edge
routes:
  main: Administration
steps:
- text: A pending invitation was created more than three days ago
  kind: condition
  unattended: true
  entities:
  - entity: invitation
    effect: reads
    facts:
    - Sent at
  contexts:
    main:
      place: 'crm-web::administration::invite-user'
- text: The Product marks the invitation expired in its daily run
  kind: product
  entities:
  - entity: invitation
    effect: changes
    from: Pending
    to: Expired
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::invite-user'
---

# An invitation expires

## Trigger

The daily run finds an invitation nobody followed for three days.

## Outcome

The invitation is expired and its link no longer works.
