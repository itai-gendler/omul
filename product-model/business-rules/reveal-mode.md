---
appliesTo:
- type: entity
  id: presentation
  facts:
  - Results visibility
- type: capability
  id: submit-answer
- type: capability
  id: reveal-results
- type: capability
  id: view-shared-results
references:
- kind: code
  role: implementation
  target: server/schemas.ts#effectiveResultsVisibility
- kind: doc
  role: intent
  target: docs/api.md
  title: The deck's reveal mode
---

# A tally reaches the room according to the slide's reveal mode

Instant publishes the tally as answers land, On click only once the presenter reveals the slide, and Private never. A slide follows the presentation's mode unless it sets its own. Ending a presentation reveals nothing.
