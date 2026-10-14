---
kind: validation
routes:
  main: Administration
steps:
- text: The Manager enters an address and a wrong password and chooses Create
  kind: actor
  actor: manager
  entities:
  - entity: email-account
    effect: reads
    facts:
    - Email address
  contexts:
    main:
      place: 'crm-web::administration::email-accounts'
- text: 'The Product refuses: Failed to create email account: invalid credentials'
  kind: condition
  actor: manager
  entities:
  - entity: email-account
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::administration::email-accounts'
---

# Add an email account with wrong credentials

## Trigger

A Manager mistypes the password.

## Outcome

No account is saved.
