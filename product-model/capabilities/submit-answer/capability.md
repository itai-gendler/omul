---
availability:
- place: web::audience
domain: participation
references:
- kind: code
  role: implementation
  target: src/components/ParticipantSlideView.tsx#ParticipantSlideView
- kind: code
  role: implementation
  target: server/services/presentations.ts#submitVote
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: code
  role: implementation
  target: server/schemas.ts#VOTE_REFUSAL_CODES
- kind: doc
  role: intent
  target: docs/api.md
  title: Voting and results by slide type
---

# Submit answer

A participant answers the slide in front of them: picking, writing, rating, ordering, placing, splitting points, guessing, pinning or filling in a form, and on a quiz question competing for points.
