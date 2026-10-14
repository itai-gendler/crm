---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User chooses Convert to Deal and picks an existing organization and an existing contact
  kind: actor
  actor: sales-user
  entities:
  - entity: organization
    effect: reads
    facts:
    - Organization name
  - entity: contact
    effect: reads
    facts:
    - Full name
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
- text: The Product creates the deal with the chosen contact and organization
  kind: product
  actor: sales-user
  entities:
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
    - Communication status
  - entity: contact
    effect: reads
    facts: []
  - entity: organization
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
    from: Open
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

# Convert a lead using an existing contact and organization

## Trigger

A Sales User converts a lead whose person and organization are already in the CRM.

## Outcome

The deal is linked to the existing contact and organization; no duplicates are made.

## Edge cases

- Choose Existing switched on with nothing picked → Please select an existing contact (or organization)
- Without choosing, a contact whose email matches the lead's is reused rather than duplicated
