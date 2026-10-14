---
availability:
- place: web::studio
- place: cli
domain: templates
references:
- kind: code
  role: implementation
  target: src/pages/TemplatesPage.tsx#TemplatesPage
- kind: code
  role: implementation
  target: server/templates.ts#listDeckTemplates
- kind: code
  role: implementation
  target: server/routes/templates.ts#templateRoutes
---

# Browse templates

An organizer looks through the catalog of prebuilt presentations, by category or by search.
