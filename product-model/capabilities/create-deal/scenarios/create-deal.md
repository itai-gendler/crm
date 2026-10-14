---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User enters an organization name, a person''s name, email and mobile, and the deal''s status and value'
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts:
    - Status
  - entity: organization
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
- text: 'The Product creates the organization and the contact unless ones with that name, email or mobile exist'
  kind: product
  actor: sales-user
  entities:
  - entity: organization
    effect: creates
    facts:
    - Organization name
    - Website
    - Territory
    - Industry
    - Annual revenue
    - No. of employees
  - entity: contact
    effect: creates
    facts:
    - First name
    - Last name
    - Email addresses
    - Phone numbers
    - Organization
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
- text: The Sales User creates the deal with that contact as primary
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: creates
    to: Open
    facts:
    - Organization
    - Status
    - Deal owner
    - Deal value
    - Expected deal value
    - Expected closure date
    - Contacts
    - Primary email
    - Primary mobile no
  - entity: contact
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deals'
- text: 'The Product sets its probability, assigns its owner, starts its SLA and opens its page'
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    facts:
    - Probability
    - Assigned to
    - Communication status
    - SLA
    - SLA status
    - Response by
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Create a deal with a new contact and organization

## Trigger

A Sales User chooses Create on Deals.

## Outcome

The Sales User is on the new deal's page; the deal is in Qualification with its contact as primary.

## Decision points

### Automatic assignment

Does an enabled assignment rule for deals match today?

- A rule matches → it also assigns the deal by its routing
- None matches → only the owner is assigned
