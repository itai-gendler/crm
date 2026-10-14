---
id: frappe-crm
summary: 'Open-source CRM for sales teams: leads and deals with status pipelines, contacts and organizations, tasks, notes, calls, email and WhatsApp, SLAs and assignment rules.'
category: crm
tags:
- crm
- sales
- pipeline
- leads
- deals
authors:
- name: Frappe Technologies
  url: 'https://frappe.io'
license: AGPL-3.0-only
languages:
- en
- ar
- bg
- bs
- cs
- da
- de
- eo
- es
- fa
- fr
- hi
- hr
- hu
- id
- it
- km
- ko
- mn
- my
- nb
- nl
- pl
- pt
- pt-BR
- ro
- ru
- sl
- sr
- sr-CS
- sv
- ta
- th
- tr
- uk
- uz
- vi
- zh
- zh-TW
limitations:
- 'Lead and deal statuses, lost reasons, lead sources, industries and territories are configured in the Frappe desk, not in the CRM''s own settings.'
- 'Email goes through the site''s email accounts; the CRM keeps no mailbox of its own.'
- Calls go through Twilio or Exotel and WhatsApp messages through a separately installed WhatsApp app.
- 'People sign in with their site account on the site''s login page.'
references:
- kind: code
  role: implementation
  target: README.md
- kind: code
  role: implementation
  target: crm/hooks.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
---

# Frappe CRM

Frappe CRM is a sales CRM for teams of any size. Salespeople capture leads by hand, from email, WhatsApp or calls, work them on one page with emails, comments, notes, tasks, calls and WhatsApp messages, and convert them into deals that move through a configurable pipeline of statuses on lists and kanban boards. Contacts and organizations are kept once and linked to the deals they take part in. Managers and Admins set SLA policies that time the team's responses in working hours, assignment rules that share new leads and deals out, the sales hierarchy that decides who sees whose pipeline, and who holds which role.

## Intent

A simple, affordable, open-source CRM for modern sales teams with unlimited users: a clean, customizable tool for the core CRM activities that helps build strong customer relationships while keeping things organised. It bridges the gap left by CRMs that are too complex, too generic or locked behind steep pricing, is easy to adapt to a team's own workflow, and puts every action and detail of a lead or deal on one page, with kanban boards and custom views to track progress.
