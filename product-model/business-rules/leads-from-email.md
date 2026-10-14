---
appliesTo:
- type: entity
  id: lead
  effect: creates
- type: entity
  id: email-account
  facts:
  - Create leads from incoming emails
references:
- kind: code
  role: implementation
  target: crm/utils/__init__.py
- kind: code
  role: implementation
  target: crm/install.py
---

# Only a new, human sender's email starts a lead

An incoming email that belongs to no lead or deal starts a lead only when its account has Create Lead from Incoming Emails on, no lead has the sender's address, and the sender is not an automated address such as no-reply or mailer-daemon.
