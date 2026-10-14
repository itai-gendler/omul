---
appliesTo:
- type: entity
  id: slide-comment
  effect: creates
permits:
- related:
  - &id001
    verb: has
    entity: slide
  - &id002
    verb: has
    entity: presentation
  - verb: owns
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
    is-not: Can view
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
  target: server/schemas.ts#canWriteDeckComments
---

# Only accounts with comment or edit access comment on a slide

The owner, an account the presentation is shared with at Can comment or Can edit, and the members of its workspace write comments. The edit link alone, with no account behind it, does not reach the comments.
