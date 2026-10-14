---
availability:
- place: 'crm-web::sales-workspace'
references:
- kind: code
  role: implementation
  target: frontend/src/components/CommunicationArea.vue
- kind: code
  role: implementation
  target: frontend/src/components/EmailEditor.vue
- kind: code
  role: implementation
  target: frontend/src/components/Modals/EmailTemplateSelectorModal.vue
- kind: code
  role: implementation
  target: crm/utils/__init__.py
---

# Send email

Email a lead's or deal's person from its page, from one's own address or an account, optionally from a template for that record type, with CC, BCC and attachments. The email is kept on the record.
