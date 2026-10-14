---
appliesTo:
- type: entity
  id: presentation
  facts:
  - Closed slides
- type: capability
  id: submit-answer
- type: capability
  id: add-answer-upvote
- type: capability
  id: close-submissions
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#setSlideParticipation
- kind: doc
  role: intent
  target: docs/requirements/REQ111.md
---

# A closed slide takes no answers and keeps those it has

While the presenter has a slide closed, submissions and upvotes on it are refused with a stated reason; every answer already given stays.
