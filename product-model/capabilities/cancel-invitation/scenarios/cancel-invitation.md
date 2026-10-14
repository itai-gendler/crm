---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager chooses Delete Invitation on a pending invite
  kind: actor
  actor: manager
  entities:
  - entity: invitation
    effect: removes
    from: Pending
  contexts:
    main:
      place: 'crm-web::administration::invite-user'
---

# Delete a pending invitation

## Trigger

A Manager invited the wrong address.

## Outcome

The invitation is gone and its link no longer works.
