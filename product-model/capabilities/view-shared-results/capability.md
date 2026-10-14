---
availability:
- place: web::shared-results
domain: results
references:
- kind: code
  role: implementation
  target: src/pages/SharedResultsPage.tsx#SharedResultsPage
- kind: code
  role: implementation
  target: server/services/presentations.ts#authorizeResultsLink
- kind: doc
  role: intent
  target: docs/requirements/REQ098.md
---

# View shared results

Anyone opens a presentation's read-only results page; with the presentation's results link, it shows tallies the reveal mode keeps from the room.
