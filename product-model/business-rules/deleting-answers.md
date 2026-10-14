---
appliesTo:
- type: entity
  id: answer
  effect: removes
permits:
- related:
  - &id001
    verb: receives
    entity: slide
  - &id002
    verb: has
    entity: presentation
  - verb: owns
    entity: organizer
- related:
  - *id001
  - *id002
  - verb: holds-edit-link-for
    entity: organizer
- related:
  - *id001
  - *id002
  - verb: has
    entity: collaborator
  - verb: holds
    entity: organizer
  when:
  - entity: collaborator
    fact: Level
    is: Can edit
- related:
  - *id001
  - *id002
  - verb: owns
    entity: workspace
  - verb: has
    entity: workspace-member
  - verb: holds
    entity: organizer
references:
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: code
  role: implementation
  target: server/services/presentations.ts#deleteSubmittedAnswer
---

# Only a presentation's editors delete an answer the room submitted

An answer on a Word Cloud or Open Text slide is deleted by its owner, whoever holds its edit link, an account it is shared with at Can edit, and every member of the workspace that owns it.
