---
appliesTo:
- type: entity
  id: presentation
- type: capability
  id: reset-results
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#resetPresentation
---

# Resetting results clears the session and keeps the presentation

Reset results deletes every answer, upvote, question and chat message and the names participants gave, reopens every slide, lifts every reveal and the blank screen, and returns the presentation to Draft; its slides, settings and join code stay.
