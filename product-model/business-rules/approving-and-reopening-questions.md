---
appliesTo:
- type: entity
  id: audience-question
  effect: changes
  to: Open
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
  target: server/services/presentations.ts#approveQuestion
---

# Only a presentation's editors approve or reopen audience questions

Publishing a question that waits for approval, and putting an answered one back in the queue, are done by its owner, whoever holds its edit link, an account it is shared with at Can edit, and every member of the workspace that owns it.
