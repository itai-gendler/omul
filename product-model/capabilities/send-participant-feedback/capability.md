---
availability:
- place: web::audience
domain: participation
references:
- kind: code
  role: implementation
  target: src/components/ParticipantFeedbackPrompt.tsx#ParticipantFeedbackPrompt
- kind: code
  role: implementation
  target: src/feedback-prompt.ts#shouldAskForParticipantFeedback
- kind: code
  role: implementation
  target: server/routes/feedback.ts#createFeedbackRoutes
- kind: doc
  role: intent
  target: docs/requirements/REQ186.md
---

# Send participant feedback

After a session ends, a sampled participant is asked once what they think of omul and may answer anonymously. Offered while the deployment sets a share of participants to ask.
