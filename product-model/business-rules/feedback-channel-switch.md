---
appliesTo:
- type: entity
  id: feedback
  effect: creates
permits:
- actors:
  - organizer
  when:
  - entity: deployment-settings
    fact: Feedback channel
    is: 'On'
references:
- kind: code
  role: implementation
  target: server/routes/feedback.ts#createFeedbackRoutes
- kind: code
  role: implementation
  target: server/feedback-store.ts#feedbackChannelOn
---

# Feedback is taken from the app menu only while the deployment turns the channel on

Sending feedback about omul exists only while the operator turns the feedback channel on.
