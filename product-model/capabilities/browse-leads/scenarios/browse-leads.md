---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User opens Leads
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
- text: 'The Product lists the unconverted leads the Sales User may see, in the default view'
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Full name
    - Organization
    - Status
    - Email
    - Mobile no.
    - Assigned to
    - SLA status
    - First response time
  - entity: view
    effect: reads
    facts: []
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
- text: The Sales User switches to the kanban board and filters by Lead owner
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: reads
    facts:
    - Full name
    - Status
    - Lead owner
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
---

# Browse leads

## Trigger

A Sales User opens Leads from the sidebar.

## Outcome

The Sales User sees their own and assigned unconverted leads in columns by status, filtered by owner.

## Edge cases

- No lead matches the filters → an empty list with a way to create one
- A converted lead never appears in Leads; its deal carries on

## Decision points

### Which view opens

Has the person or the CRM set a default view for leads?

- A default view is set → that view opens
- None is set → the standard list opens
