---
availability:
- place: web::studio
references:
- kind: code
  role: implementation
  target: src/components/FeedbackForm.tsx#FeedbackForm
- kind: code
  role: implementation
  target: server/routes/feedback.ts#createFeedbackRoutes
- kind: doc
  role: intent
  target: docs/requirements/REQ185.md
---

# Send feedback

An organizer sends feedback about omul itself to the people who run the instance, from the app menu. Offered while the deployment turns the feedback channel on.
