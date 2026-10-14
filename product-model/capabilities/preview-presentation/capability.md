---
availability:
- place: web::studio
domain: editor
references:
- kind: code
  role: implementation
  target: src/pages/PreviewPage.tsx#PreviewPage
- kind: code
  role: implementation
  target: server/preview.ts#generateDeckTestVotes
- kind: code
  role: implementation
  target: server/services/presentations.ts#getPreviewResults
---

# Preview presentation

An organizer runs a dry run of a whole presentation with generated test votes, without collecting anything.
