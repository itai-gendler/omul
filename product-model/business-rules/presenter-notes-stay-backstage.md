---
appliesTo:
- type: entity
  id: slide
  effect: reads
  facts:
  - Presenter notes
permits:
- related:
  - &id001
    verb: has
    entity: presentation
  - verb: owns
    entity: organizer
- related:
  - *id001
  - verb: holds-edit-link-for
    entity: organizer
- related:
  - *id001
  - verb: has
    entity: collaborator
  - verb: holds
    entity: organizer
- related:
  - *id001
  - verb: owns
    entity: workspace
  - verb: has
    entity: workspace-member
  - verb: holds
    entity: organizer
references:
- kind: code
  role: implementation
  target: server/schemas.ts#withAudienceSlides
- kind: doc
  role: intent
  target: docs/requirements/REQ090.md
---

# Only the presentation's own people read its presenter notes

Presenter notes reach the owner, whoever holds the edit link, every account the presentation is shared with, and the members of its workspace. They never reach the room.
