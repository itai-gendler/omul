---
appliesTo:
- type: entity
  id: collaborator
  effect: changes
permits:
- related:
  - &id001
    verb: has
    entity: presentation
  - verb: owns
    entity: organizer
- related:
  - *id001
  - verb: owns
    entity: workspace
  - verb: has
    entity: workspace-member
  - verb: holds
    entity: organizer
  when:
  - entity: workspace-member
    fact: Role
    is-not: Member
references:
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: doc
  role: intent
  target: docs/api.md
  title: Sharing a deck with other accounts
---

# Only the owner or a workspace admin changes what a collaborator may do

Who else a presentation reaches is decided by the account that owns it, or, for a workspace's presentation, by an Admin or Owner of the workspace. The edit link and a share at Can edit help with the presentation; they do not decide who else gets it.
