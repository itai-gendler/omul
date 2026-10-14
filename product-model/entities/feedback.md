---
references:
- kind: code
  role: implementation
  target: server/feedback-store.ts#createFeedbackStore
- kind: code
  role: implementation
  target: server/routes/feedback.ts#createFeedbackRoutes
---

# Feedback

A note about omul itself, sent to the people who run the instance from the app menu.

## Information kept

- **Rating** — one to five stars
- **Comment** — what the sender wrote, up to 2,000 characters
- **Surface** — where it was sent from: Presenter, Participant or Other
- **Language** — the language of the app when it was sent
- **Contact** — the sender's account, when they asked to be contacted
- **Sent on** — the day it was sent
