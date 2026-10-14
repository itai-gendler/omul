---
availability:
- place: web::studio
domain: presenting
references:
- kind: code
  role: implementation
  target: src/pages/PresenterPage.tsx#PresenterPage
- kind: code
  role: implementation
  target: server/services/presentations.ts#resetPresentation
- kind: doc
  role: intent
  target: docs/requirements/REQ101.md
---

# Reset results

An organizer clears everything the room submitted and returns the presentation to a draft, to run it again.
