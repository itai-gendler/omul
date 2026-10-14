---
appliesTo:
- type: entity
  id: answer
- type: capability
  id: view-results
- type: capability
  id: export-session
- type: capability
  id: preview-presentation
references:
- kind: code
  role: implementation
  target: server/schemas.ts#canReadDeckAuthoring
---

# The presentation's own people read every tally, whatever the reveal mode

The presenter view, exports and previews show every tally to the presentation's editors and the accounts it is shared with, whatever the reveal mode keeps from the room.
