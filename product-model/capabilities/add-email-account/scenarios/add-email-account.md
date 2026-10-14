---
kind: primary
routes:
  main: Administration
steps:
- text: 'The Manager picks GMail, enters the address, name and app password, and chooses which way it works'
  kind: actor
  actor: manager
  entities:
  - entity: email-account
    effect: reads
    facts:
    - Service
  contexts:
    main:
      place: 'crm-web::administration::email-accounts'
- text: The Product checks the credentials against the service and saves the account
  kind: product
  actor: manager
  entities:
  - entity: email-account
    effect: creates
    facts:
    - Account name
    - Email address
    - Service
    - Incoming
    - Outgoing
    - Default incoming
    - Default outgoing
  contexts:
    main:
      place: 'crm-web::administration::email-accounts'
---

# Add an email account

## Trigger

A Manager connects the sales inbox.

## Outcome

The account is saved: Email account created successfully.
