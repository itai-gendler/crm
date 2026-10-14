---
appliesTo:
- type: entity
  id: email-template
- type: capability
  id: send-email
references:
- kind: code
  role: implementation
  target: frontend/src/components/Modals/EmailTemplateSelectorModal.vue
---

# Only enabled templates for the record's type are offered

Writing an email from a lead offers the enabled templates for leads; from a deal, the enabled templates for deals.
