---
availability:
- place: web::audience
domain: participation
references:
- kind: code
  role: implementation
  target: src/components/Results.tsx#OpenTextResults
- kind: code
  role: implementation
  target: server/services/presentations.ts#voteOnResponse
- kind: doc
  role: intent
  target: docs/requirements/REQ025.md
---

# Add answer upvote

A participant upvotes a written answer on an Open Text slide that allows it.
