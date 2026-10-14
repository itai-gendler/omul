---
appliesTo:
- type: entity
  id: presentation
  facts:
  - Edit link
- type: capability
  id: move-presentation-to-workspace
- type: capability
  id: create-workspace-presentation
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#setPresentationWorkspace
---

# A workspace's presentation has no edit link

Moving a presentation into a workspace retires its edit link for good, and a presentation created in a workspace gets none; members reach it through their membership.
