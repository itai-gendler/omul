---
appliesTo:
- type: entity
  id: deployment-settings
  facts:
  - Prompt share
  - Prompt cooldown
- type: capability
  id: send-participant-feedback
references:
- kind: code
  role: implementation
  target: src/feedback-prompt.ts#shouldAskForParticipantFeedback
---

# A participant is asked for feedback at most once per cooldown, after a session they saw live

Only participants who saw the presentation live, fall in the deployment's share and have not been asked on that device within the cooldown are asked, once the presentation has ended.
