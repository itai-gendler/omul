---
appliesTo:
- type: entity
  id: feedback
- type: entity
  id: participant-feedback
- type: capability
  id: send-feedback
references:
- kind: code
  role: implementation
  target: server/feedback-store.ts#createFeedbackStore
---

# Feedback about omul is never shown to organizers

Feedback from the app menu and from participants is kept in the operator's own store, with the day it was sent and no presentation, participant or address; an account is kept only when its holder asks to be contacted.
