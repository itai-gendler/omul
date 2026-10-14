---
appliesTo:
- type: entity
  id: participant-feedback
  effect: creates
permits:
- actors:
  - participant
  when:
  - entity: deployment-settings
    fact: Prompt share
    present: true
references:
- kind: code
  role: implementation
  target: server/routes/feedback.ts#createFeedbackRoutes
---

# Participants are asked for feedback only while the deployment sets a share to ask

The prompt after a session exists only while the operator sets the share of participants to ask.
