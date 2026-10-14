---
entities:
- entity: feedback
  shows:
  - Rating
  - Comment
  - Surface
  - Language
  - Contact
  - Sent on
- entity: participant-feedback
  shows:
  - Rating
  - Comment
  - Language
  - Sent on
entryPoints:
- web: /app/admin/feedback
references:
- kind: code
  role: implementation
  target: src/pages/AdminFeedbackPage.tsx#AdminFeedbackPage
---

# Feedback about omul

The feedback sent about omul from the app menu and from participants after a session.
