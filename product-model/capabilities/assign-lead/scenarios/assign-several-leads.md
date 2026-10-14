---
kind: primary
routes:
  main: Sales workspace
steps:
- text: The Sales User selects leads on Leads and chooses Assign To with a colleague
  kind: actor
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Assigned to
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
- text: 'The Product makes the colleague each lead''s owner and notifies them for each'
  kind: product
  actor: sales-user
  entities:
  - entity: lead
    effect: changes
    facts:
    - Lead owner
  - entity: notification
    effect: creates
    facts:
    - Type
    - From
    - Message
    - Read
    - Linked to
  contexts:
    main:
      place: 'crm-web::sales-workspace::leads'
---

# Assign several leads at once

## Trigger

A Sales User assigns a selection of leads from the list.

## Outcome

Every selected lead is assigned to and owned by the colleague.
