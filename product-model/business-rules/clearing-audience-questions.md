---
appliesTo:
- type: entity
  id: audience-question
  effect: removes
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
  target: server/services/presentations.ts#resetPresentation
---

# Only a presentation's editors clear the room's questions

The room's questions are deleted, when results are reset, by its owner, whoever holds its edit link, an account it is shared with at Can edit, and every member of the workspace that owns it.
