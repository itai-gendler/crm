---
domain: deals
relations:
- entity: contact
  verb: includes
  cardinality: many-to-many
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
  target: crm/fcrm/doctype/crm_deal/crm_deal.py
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_deal/crm_deal.json
- kind: code
  role: implementation
  target: crm/install.py
---

# Deal

An opportunity the sales team is working toward a sale, with an organization and its contacts. Its status follows the configured deal statuses, each of one of five types; its states are those types.

## Information kept

- **Organization** — the organization the deal is with
- **Contacts** — the contacts on the deal, one of them primary
- **Primary email** — the primary contact's email
- **Primary mobile no** — the primary contact's mobile number
- **Deal owner** — the salesperson who owns the deal
- **Assigned to** — the people the deal is assigned to
- **Status** — a configured deal status such as Qualification, Demo/Making, Proposal/Quotation, Negotiation, Ready to Close, Won or Lost
- **Probability** — the chance of winning, defaulting to the status's probability
- **Deal value** — the deal's value
- **Expected deal value** — the value the team expects to close
- **Expected closure date** — when the team expects to close
- **Closed date** — when the deal was won
- **Currency** — the deal's currency
- **Exchange rate** — the rate to the CRM's currency
- **Next step** — the next thing to do
- **Lost reason** — why the deal was lost; required while it is lost
- **Lost notes** — an explanation, required when the lost reason is Other
- **Lead** — the lead the deal was converted from
- **Products** — products sold with quantity, rate and discount
- **Net total** — the products' total after discounts
- **Website** — the organization's website
- **Territory** — the sales territory
- **Source** — where the business came from
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
