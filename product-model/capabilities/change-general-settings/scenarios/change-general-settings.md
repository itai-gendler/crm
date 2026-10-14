---
kind: primary
routes:
  main: Administration
steps:
- text: The Manager turns on marking records replied on response and sets the timeline to Newest First
  kind: actor
  actor: manager
  entities:
  - entity: crm-settings
    effect: changes
    facts:
    - Mark lead/deal as replied on response
    - Timeline sort order
  contexts:
    main:
      place: 'crm-web::administration::general-settings'
---

# Change general settings

## Trigger

A Manager tunes how the CRM treats communication.

## Outcome

Emails sent from now on mark their lead or deal Replied, and timelines show the newest first.
