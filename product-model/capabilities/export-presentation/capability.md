---
availability:
- place: web::studio
domain: presentations
references:
- kind: code
  role: implementation
  target: src/pages/HomePage.tsx#HomePage
- kind: code
  role: implementation
  target: src/api.ts#buildExportPayload
---

# Export presentation

An organizer downloads a presentation as a .omul.json file another omul can import.
