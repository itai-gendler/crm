---
domain: sla-policies
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_service_level_agreement/crm_service_level_agreement.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_service_level_agreement/crm_service_level_agreement.json
---

# SLA policy

A service level agreement for leads or for deals: how soon the sales team must respond, counted in working hours.

## Information kept

- **Name** — the policy's name
- **Apply on** — Lead or Deal
- **Default** — whether it applies when no other policy does
- **Conditions** — which leads or deals it covers
- **Start date** — when it starts to apply
- **End date** — when it stops applying
- **Priorities** — per communication status, the first response time; one is the default priority
- **Working hours** — the working days with their start and end times
- **Holiday list** — days that never count
- **Rolling responses** — whether every later response is timed as well as the first

## States

### Enabled

Applied to new and saved leads or deals it matches.

### Disabled

Not applied.
