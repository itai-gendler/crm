---
appliesTo:
- type: entity
  id: email-account
  effect: creates
references:
- kind: code
  role: implementation
  target: crm/api/settings.py
---

# An email account is saved only with working credentials

Adding an account from a mail service checks its credentials against the service's incoming server first; an account whose credentials fail is not saved.
