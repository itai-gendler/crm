---
domain: users
relations:
- entity: hierarchy-entry
  verb: holds
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: crm/api/user.py
- kind: code
  role: implementation
  target: crm/api/session.py
---

# CRM user

A person's account on the site and their role in the CRM. A person holds one of the three CRM roles, or none.

## Information kept

- **Full name** — the person's name
- **Email** — the person's email address, which signs them in
- **Image** — the person's picture

## States

### Without CRM access

The person has a site account but no CRM role.

### Sales User

The person holds the Sales User role.

### Manager

The person holds the Sales Manager role, with Sales User.

### Admin

The person holds the System Manager role, with Sales Manager and Sales User.
