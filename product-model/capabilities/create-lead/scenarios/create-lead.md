---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User enters a first name, email, mobile number, company name, website and status, and creates the lead'
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: creates
    to: Open
    facts:
    - First name
    - Last name
    - Email
    - Mobile no.
    - Organization
    - Website
    - No. of employees
    - Status
    - Lead owner
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
- text: 'The Product names the lead, assigns its owner, starts its SLA and opens its page'
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Full name
    - Assigned to
    - Communication status
    - SLA
    - SLA status
    - Response by
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
---

# Create a lead from Leads

## Trigger

A Sales User chooses Create on Leads.

## Outcome

The Sales User is on the new lead's page; the lead is New, owned by and assigned to them unless they chose another owner.

## Edge cases

- A website without a scheme is saved with https://
- The lead's email equals the chosen lead owner's email → refused

## Decision points

### SLA

Does an enabled SLA policy for leads match the new lead?

- One matches → its first response is due by the policy's working hours
- None matches → the lead has no SLA

### Automatic assignment

Does an enabled assignment rule for leads match, on one of its assignment days?

- A rule matches → it assigns the lead by its routing, as well as the owner
- None matches → only the owner is assigned
