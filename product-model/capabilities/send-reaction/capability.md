---
availability:
- place: web::audience
domain: audience-channels
references:
- kind: code
  role: implementation
  target: src/components/ReactionBar.tsx#ReactionBar
- kind: code
  role: implementation
  target: server/services/presentations.ts#sendReaction
- kind: doc
  role: intent
  target: docs/requirements/REQ077.md
---

# Send reaction

A participant sends a reaction that crosses the shared screen.
