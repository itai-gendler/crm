---
domain: invitations
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_invitation/crm_invitation.py
---

# Invitation

An emailed invitation to join the CRM with a role.

## Information kept

- **Email** — who is invited
- **Role** — Sales User, Manager or Admin
- **Invited by** — who sent it
- **Sent at** — when the email went out
- **Accepted at** — when it was accepted

## States

### Pending

Sent and not yet followed.

### Accepted

Followed; the person holds the role.

### Expired

Not followed within three days.
