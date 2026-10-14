---
appliesTo:
- type: entity
  id: audience-question
  effect: changes
  to: Answered
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
  when:
  - entity: collaborator
    fact: Level
    is: Can edit
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
  target: server/routes/presentations.ts#presentationRoutes
- kind: code
  role: implementation
  target: server/services/presentations.ts#setQuestionAnswered
---

# Only a presentation's editors mark audience questions answered

A question from the room is marked answered by its owner, whoever holds its edit link, an account it is shared with at Can edit, and every member of the workspace that owns it.
