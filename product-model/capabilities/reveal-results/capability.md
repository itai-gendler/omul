---
availability:
- place: web::studio
domain: presenting
references:
- kind: code
  role: implementation
  target: src/components/PresenterSlideView.tsx#PresenterSlideView
- kind: code
  role: implementation
  target: server/services/presentations.ts#setSlideRevealed
- kind: doc
  role: intent
  target: docs/requirements/REQ016.md
---

# Reveal results

An organizer publishes a slide's tally to the room on a slide whose results wait for a click.
