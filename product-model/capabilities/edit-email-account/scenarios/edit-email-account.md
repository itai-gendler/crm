---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Manager turns an account''s incoming off and chooses Update Account'
  kind: actor
  actor: manager
  entities:
  - entity: email-account
    effect: changes
    facts:
    - Incoming
  contexts:
    main:
      place: 'crm-web::administration::email-accounts'
---

# Edit an email account

## Trigger

A Manager stops an account from receiving.

## Outcome

Email account updated successfully.
