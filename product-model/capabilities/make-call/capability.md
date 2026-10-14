---
availability:
- place: 'crm-web::sales-workspace'
references:
- kind: code
  role: implementation
  target: frontend/src/components/Telephony/CallUI.vue
- kind: code
  role: implementation
  target: crm/integrations/twilio/api.py
- kind: code
  role: implementation
  target: crm/integrations/exotel/handler.py
- kind: code
  role: implementation
  target: crm/integrations/api.py
---

# Make call

Call a lead's, deal's or contact's mobile number through Twilio in the browser or Exotel to one's own phone, and have the call recorded on the record.
