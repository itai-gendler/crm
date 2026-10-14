---
relations:
- entity: note
  verb: records
  cardinality: one-to-many
- entity: task
  verb: leads to
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_call_log/crm_call_log.py
---

# Call log

The record of a phone call with a lead, deal or contact, made through Twilio or Exotel or logged by hand.

## Information kept

- **Type** — Incoming or Outgoing
- **Status** — how the call went, such as Completed, No Answer or Busy
- **Caller** — who called
- **Receiver** — who answered
- **From** — the calling number
- **To** — the called number
- **Duration** — how long the call lasted
- **Start time** — when it began
- **Recording** — the call recording, when the provider keeps one
- **Medium** — Manual, Twilio or Exotel
- **Linked to** — the lead or deal it belongs to
- **Call notes** — notes taken about the call
- **Call tasks** — tasks created from the call
