---
references:
- kind: code
  role: implementation
  target: server/feedback-store.ts#createFeedbackStore
- kind: code
  role: implementation
  target: src/feedback-prompt.ts#shouldAskForParticipantFeedback
---

# Participant feedback

A participant's anonymous answer, after a session ends, to the question what they think of omul.

## Information kept

- **Rating** — one to five stars
- **Comment** — what they wrote, up to 2,000 characters
- **Language** — the presentation's language
- **Sent on** — the day it was sent
