---
availability:
- place: web::studio
domain: presenting
references:
- kind: code
  role: implementation
  target: src/components/ResultsLinkDialog.tsx#ResultsLinkDialog
- kind: code
  role: implementation
  target: server/services/presentations.ts#mintResultsLink
- kind: doc
  role: intent
  target: docs/requirements/REQ098.md
---

# Create results link

An organizer creates a read-only link to a presentation's results, or replaces the one that exists.
