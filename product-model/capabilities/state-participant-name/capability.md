---
availability:
- place: web::audience
domain: participation
references:
- kind: code
  role: implementation
  target: src/components/ParticipantName.tsx#ParticipantNameGate
- kind: code
  role: implementation
  target: server/services/presentations.ts#stateParticipantName
- kind: doc
  role: intent
  target: docs/requirements/REQ076.md
---

# State participant name

A participant says who they are on a presentation that asks for names, and may change it.
