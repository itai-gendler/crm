---
kind: primary
result: achieved
routes:
  main: Sales workspace
steps:
- text: The Sales User creates the lead with a first name and company details
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
  capability: create-lead
- text: 'The Product opens the new lead''s page'
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
  capability: create-lead
- text: The Sales User converts the lead to a deal
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: creates
    to: Open
    facts:
    - Organization
    - Contacts
    - Deal owner
    - Status
    - Lead
  - entity: lead
    effect: changes
    from: Open
    to: Won
    facts:
    - Status
    - Converted
  contexts:
    main:
      place: 'crm-web::sales-workspace::lead'
  capability: convert-lead
- text: 'The Product opens the new deal''s page'
  kind: product
  actor: sales-user
  entities:
  - entity: deal
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
  capability: convert-lead
- text: The Sales User moves the deal to Proposal/Quotation
  kind: actor
  actor: sales-user
  entities:
  - entity: deal
    effect: changes
    from: Open
    to: Ongoing
    facts:
    - Status
  contexts:
    main:
      place: 'crm-web::sales-workspace::deal'
  capability: change-deal-status
---

# Create a lead, convert it and advance the deal

## Trigger

A Sales User creates a lead on Leads.

## Outcome

The lead is converted, and the deal the Product opened is in Proposal/Quotation.
