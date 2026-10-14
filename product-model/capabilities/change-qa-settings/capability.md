---
availability:
- place: web::studio
domain: q-and-a
references:
- kind: code
  role: implementation
  target: src/components/QAPanel.tsx#QALayerControls
- kind: code
  role: implementation
  target: server/services/presentations.ts#setQASettings
- kind: doc
  role: intent
  target: docs/requirements/REQ036.md
---

# Change Q&A settings

An organizer switches the room's questions on or off, chooses who reads them, and chooses whether each waits for approval.
