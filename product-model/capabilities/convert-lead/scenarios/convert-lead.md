---
kind: primary
routes:
  main: Sales workspace
steps:
- text: 'The Sales User chooses Convert to Deal on the lead and fills the deal''s required fields'
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Full name
    - Organization
    - Email
    - Status
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product creates the organization and contact from the lead, and the deal with the lead''s details'
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
    - Designation
  - entity: deal
    effect: creates
    to: Open
    facts:
    - Organization
    - Contacts
    - Primary email
    - Primary mobile no
    - Deal owner
    - Assigned to
    - Status
    - Lead
    - Products
    - Net total
    - Website
    - Territory
    - Source
    - Communication status
    - SLA
    - SLA status
    - Response by
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: 'The Product marks the lead Qualified and converted, and opens the new deal'
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    from: Ongoing
    to: Won
    facts:
    - Status
    - Converted
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
---

# Convert a lead to a deal

## Trigger

A Sales User converts a lead that is not lost.

## Outcome

The Sales User is on the new deal's page; the lead is converted and leaves Leads.

## Edge cases

- A lead that already has a deal can be converted again; another deal is created
- Deal fields required for conversion that are left empty → refused with the field's name

## Decision points

### SLA carried over

Had the lead been responded to?

- Yes → the deal keeps the lead's SLA timing and communication status
- No → the deal starts its own SLA
