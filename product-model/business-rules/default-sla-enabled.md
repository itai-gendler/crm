---
appliesTo:
- type: entity
  id: sla-policy
  effect: changes
  to: Disabled
permits:
- actors:
  - manager
  - admin
  when:
  - fact: Default
    is: 'No'
references:
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Sla/SlaPolicyView.vue
- kind: code
  role: implementation
  target: frontend/src/components/Settings/Sla/SlaPolicyList.vue
---

# The default SLA policy is never disabled

A policy set as default cannot be switched off, and making a policy default enables it.
