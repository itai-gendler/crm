---
domain: email-accounts
references:
- kind: code
  role: implementation
  target: crm/api/settings.py
- kind: code
  role: implementation
  target: crm/install.py
---

# Email account

A mailbox the CRM sends from and receives into.

## Information kept

- **Account name** — its name
- **Email address** — its address
- **Service** — GMail, Outlook, Sendgrid, SparkPost, Yahoo, Yandex or Frappe Mail
- **Incoming** — whether it receives
- **Outgoing** — whether it sends
- **Default incoming** — whether it is the default inbox
- **Default outgoing** — whether it is the default sender
- **Create leads from incoming emails** — whether an email from an unknown sender starts a lead
