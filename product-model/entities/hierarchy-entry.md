---
domain: sales-hierarchy
relations:
- entity: hierarchy-entry
  verb: reports to
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_sales_hierarchy/crm_sales_hierarchy.py
- kind: code
  role: implementation
  target: docs/user-hierarchy.md
---

# Hierarchy entry

A Manager's or Sales User's place in the sales hierarchy, the reporting tree that decides who sees whose leads and deals.

## Information kept

- **Person** — the Manager or Sales User placed here
- **Reports to** — the entry above it, if any
