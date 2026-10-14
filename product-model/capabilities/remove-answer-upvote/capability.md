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
---

# Remove answer upvote

A participant takes back their upvote on a written answer.
