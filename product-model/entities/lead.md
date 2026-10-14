---
domain: leads
relations:
- entity: deal
  verb: is converted into
  cardinality: one-to-many
- entity: note
  verb: has
  cardinality: one-to-many
- entity: task
  verb: has
  cardinality: one-to-many
- entity: call-log
  verb: has
  cardinality: one-to-many
- entity: comment
  verb: has
  cardinality: one-to-many
- entity: email-message
  verb: has
  cardinality: one-to-many
- entity: whatsapp-message
  verb: has
  cardinality: one-to-many
- entity: attachment
  verb: has
  cardinality: one-to-many
- entity: activity
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_lead/crm_lead.json
- kind: code
  role: implementation
  target: crm/install.py
---

# Lead

A person or organization that may buy, before the sales team qualifies them into a deal. Its status follows the configured lead statuses, each of which is of one of five types; its states are those types.

## Information kept

- **First name** — the person's first name; required in the CRM
- **Last name** — the person's last name
- **Full name** — the name the lead is known by: the person's name, else the organization, else the email's name
- **Email** — the person's email address; never the lead owner's own address
- **Mobile no.** — the number calls and WhatsApp messages go to
- **Phone** — another phone number
- **Organization** — the name of the organization the person belongs to
- **Website** — the organization's website
- **Job title** — the person's job title
- **Industry** — the organization's industry
- **Territory** — the sales territory
- **Source** — where the lead came from, such as Email or WhatsApp
- **No. of employees** — the organization's size band
- **Annual revenue** — the organization's annual revenue
- **Image** — the lead's picture
- **Lead owner** — the salesperson who owns the lead
- **Assigned to** — the people the lead is assigned to
- **Status** — a configured lead status such as New, Contacted, Nurture, Qualified, Unqualified or Junk
- **Lost reason** — why the lead was lost; required while it is lost
- **Lost notes** — an explanation, required when the lost reason is Other
- **Converted** — whether the lead has become a deal
- **Products** — products of interest with quantity, rate and discount
- **Net total** — the products' total after discounts
- **SLA** — the SLA policy applied to it, if any
- **SLA status** — First Response Due, Rolling Response Due, Fulfilled or Failed
- **Response by** — when the next response is due under its SLA policy
- **First responded on** — when the sales team first responded
- **First response time** — working time from the SLA start to the first response
- **Communication status** — Open while the prospect waits for the sales team, Replied once they have answered

## States

### Open

Its status is of the Open type, such as New or Qualification: nobody has worked it yet.

### Ongoing

Its status is of the Ongoing type: the sales team is working it.

### On Hold

Its status is of the On Hold type.

### Won

Its status is of the Won type.

### Lost

Its status is of the Lost type; a lost reason is recorded.
