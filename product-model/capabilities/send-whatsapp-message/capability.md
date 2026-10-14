---
availability:
- place: 'crm-web::sales-workspace'
- place: whatsapp
references:
- kind: code
  role: implementation
  target: crm/api/whatsapp.py
- kind: code
  role: implementation
  target: frontend/src/components/Activities/Activities.vue
- kind: code
  role: implementation
  target: frontend/src/components/Modals/WhatsAppTemplateSelectorModal.vue
---

# Send WhatsApp message

Exchange WhatsApp messages on a lead or deal: a salesperson sends text, media or an approved template to its mobile number, or replies to a message; a prospect writes to the business number and the message lands on their lead or deal.
