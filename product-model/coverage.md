---
scope: 'The CRM app''s sales workspace, administration settings, invitations, email and WhatsApp intake, and the server code behind them.'
method: 'Static inspection of source, tests and documentation at the pinned commit; nothing was run.'
covered:
- description: 'Lead, deal, contact, organization, note, task, call log, notification, invitation, view, SLA and sales hierarchy records with their server rules'
  paths:
  - crm/fcrm/doctype/
  - crm/overrides/
  - crm/permissions/
- description: 'Server endpoints and document hooks for activities, assignments, comments, contacts, notifications, users, invitations, email accounts and WhatsApp'
  paths:
  - crm/api/
  - crm/utils/
  - crm/hooks.py
  - crm/install.py
- description: 'Calls and call recordings through Twilio and Exotel, and the in-call panels'
  paths:
  - crm/integrations/api.py
  - crm/integrations/twilio/
  - crm/integrations/exotel/
  - frontend/src/components/Telephony/
- description: 'The web app''s routing, pages, record views, activity panels, dialogs, lists and stores'
  paths:
  - frontend/src/router.js
  - frontend/src/pages/
  - frontend/src/components/Activities/
  - frontend/src/components/Modals/
  - frontend/src/components/ListViews/
  - frontend/src/components/Kanban/
  - frontend/src/stores/
  - frontend/src/utils/navigation.js
- description: 'Settings pages for users, invitations, the sales hierarchy, email, assignment rules, SLA policies and general settings'
  paths:
  - frontend/src/components/Settings/
- description: The CRM page and invitation email served by the site
  paths:
  - crm/www/crm.py
  - crm/templates/emails/crm_invitation.html
- description: The sales hierarchy guide
  paths:
  - docs/user-hierarchy.md
exclusions:
- description: 'Build, packaging, CI, containers, editor settings and release tooling'
  paths:
  - .github/
  - docker/
  - .devcontainer/
  - .vscode/
  - scripts/
  - package.json
  - yarn.lock
  - pyproject.toml
  - .releaserc
  - .mergify.yml
  - crowdin.yml
  - commitlint.config.cjs
  - codecov.yml
- description: Automated tests and end-to-end suites
  paths:
  - e2e/
  - frontend/tests/
  - crm/tests/
  - playwright.config.ts
- description: 'Translation catalogues, reflected in the product''s languages'
  paths:
  - crm/locale/
- description: Database patches and upgrades
  paths:
  - crm/patches/
  - crm/patches.txt
- description: 'Usage telemetry, demo data and onboarding prompts'
  paths:
  - crm/telemetry.py
  - crm/demo/
  - crm/api/onboarding.py
  - crm/api/live_demo.py
  - frontend/src/pages/PersonaForm.vue
  - frontend/src/pages/Welcome.vue
- description: 'Icons, the vendored UI kit and its submodule'
  paths:
  - frontend/src/components/Icons/
  - frontend/src/components/frappe-ui/
- description: Agent working notes
  paths:
  - .pi/
  - AGENTS.md
- description: 'The command palette, a shortcut to behavior mapped elsewhere'
  paths:
  - frontend/src/components/CommandPalette/
  - crm/api/command_palette.py
unmapped:
- description: Workflow automations
  paths:
  - crm/automation/
  - frontend/src/components/Settings/WorkflowAutomations/
- description: 'Enrichment of leads, deals and organizations from their websites'
  paths:
  - crm/domain_enrichment/
  - frontend/src/components/Settings/Enrichment/
  - frontend/src/components/EnrichFromWebsite.vue
- description: Lead syncing from external sources
  paths:
  - crm/lead_syncing/
  - frontend/src/components/Settings/LeadSyncing/
- description: 'The accounting integration, quotations and the product catalogue'
  paths:
  - crm/integrations/erpnext/
  - frontend/src/components/Settings/ERPNextSettings.vue
  - frontend/src/components/Activities/QuotationsList.vue
- description: Lead capture web forms and the form builder
  paths:
  - crm/www/crm_form.py
  - crm/www/crm_form.html
  - crm/api/form.py
  - frontend/src/components/Settings/Forms/
- description: The dashboard and its settings
  paths:
  - crm/api/dashboard.py
  - frontend/src/components/Dashboard/
  - frontend/src/components/Settings/DashboardSettings.vue
- description: Data import
  paths:
  - frontend/src/pages/DataImport.vue
- description: 'Field layouts, quick entry, side panel layouts and form scripts'
  paths:
  - frontend/src/components/FieldLayout/
  - frontend/src/components/FieldLayoutEditor.vue
  - frontend/src/components/SidePanelLayoutEditor.vue
  - frontend/src/data/
  - frontend/src/doctypes/
- description: Telephony and WhatsApp settings
  paths:
  - frontend/src/components/Settings/Telephony/
  - frontend/src/components/Settings/WhatsAppSettings.vue
- description: 'Profile, preferences, password, brand, home actions and system defaults'
  paths:
  - frontend/src/components/Settings/Profile/
  - frontend/src/components/Settings/PreferencesSettings.vue
  - frontend/src/components/Settings/BrandSettings.vue
  - frontend/src/components/Settings/HomeActions.vue
  - frontend/src/components/Settings/DefaultsSettings.vue
- description: Event reminders
  paths:
  - crm/api/event.py
limitations: []
---

# Coverage
