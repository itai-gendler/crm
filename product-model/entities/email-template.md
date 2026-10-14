---
domain: email-templates
references:
- kind: code
  role: implementation
  target: crm/overrides/email_template.py
- kind: code
  role: implementation
  target: crm/install.py
---

# Email template

A reusable email for leads or for deals.

## Information kept

- **Name** — the template's name
- **For** — Lead or Deal
- **Subject** — the subject, which may use the record's fields
- **Content type** — Rich Text or HTML
- **Content** — the body, which may use the record's fields

## States

### Disabled

Not offered when writing an email.

### Enabled

Offered when writing an email for its record type.
