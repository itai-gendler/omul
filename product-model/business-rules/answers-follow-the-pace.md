---
appliesTo:
- type: entity
  id: presentation
  facts:
  - Pace
- type: capability
  id: submit-answer
- type: capability
  id: send-audience-question
- type: capability
  id: send-reaction
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#submitVote
- kind: doc
  role: intent
  target: docs/requirements/REQ082.md
---

# A presenter-paced presentation takes answers only while live; an audience-paced one until it ends

With Presenter pace the room answers only while the presentation is Live. With Audience pace participants answer from the moment they join, in Draft or Live, until it ends. Questions, upvotes, reactions and chat follow the same rule.
