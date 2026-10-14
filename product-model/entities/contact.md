---
domain: contacts
references:
- kind: code
  role: implementation
  target: crm/overrides/contact.py
- kind: code
  role: implementation
  target: crm/api/contact.py
---

# Contact

A person the business deals with, kept once and linked to the deals they take part in.

## Information kept

- **First name** — the person's first name
- **Last name** — the person's last name
- **Full name** — the person's full name
- **Salutation** — how to address them
- **Gender** — the person's gender
- **Designation** — their job title
- **Email addresses** — their email addresses, one of them primary
- **Phone numbers** — their phone and mobile numbers, one of each primary
- **Organization** — the organization they belong to
- **Image** — their picture
