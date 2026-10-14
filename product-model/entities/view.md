---
references:
- kind: code
  role: implementation
  target: crm/fcrm/doctype/crm_view_settings/crm_view_settings.py
---

# View

A saved way to see one of the CRM's lists: a list, kanban board or grouped list with its filters, sort and columns. A view is private to its owner until made public.

## Information kept

- **Label** — the view's name
- **View type** — List, Kanban or Group By
- **List** — the list it shows: leads, deals, contacts, organizations, notes, tasks or call logs
- **Filters** — which records it shows
- **Sort** — the order
- **Columns** — the columns shown
- **Group by** — the field a grouped list groups by
- **Kanban column** — the field a board's columns follow
- **Icon** — its icon
- **Public** — whether everyone sees it
- **Pinned** — whether it sits in the sidebar
- **Default** — whether it opens first for that list
