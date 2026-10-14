---
appliesTo:
- type: entity
  id: slide
  facts:
  - Correct answers
- type: capability
  id: generate-draft-presentation
references:
- kind: code
  role: implementation
  target: server/deck-generator.ts#GeneratedSlideSchema
- kind: doc
  role: intent
  target: docs/api.md
  title: The output is a draft
---

# A drafted presentation has no answer marked correct

A presentation drafted from a prompt has no correct answer on any slide; the organizer marks the answer key.
