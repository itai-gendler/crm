---
singleton: true
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/fcrm_settings/fcrm_settings.json
---

# CRM settings

The CRM's own settings, kept once per site.

## Information kept

- **Sales hierarchy** — whether lead and deal visibility follows the sales hierarchy
- **Forecasting** — whether deals must carry an expected deal value and expected closure date
- **Auto update expected deal value** — whether a deal's expected deal value follows its products' total
- **Currency** — the currency deal values are converted to
- **Update timestamp on new communication** — whether a new email or comment marks a lead or deal as modified
- **Mark lead/deal as replied on response** — whether an email sent from the CRM sets the communication status to Replied
- **Reopen lead/deal on new communication** — whether an incoming email sets the communication status back to Open
- **Timeline timestamp format** — Relative or Exact
- **Timeline sort order** — Oldest First or Newest First
