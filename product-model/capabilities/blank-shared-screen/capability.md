---
availability:
- place: web::studio
domain: presenting
references:
- kind: code
  role: implementation
  target: src/components/LiveRoom.tsx#AudienceBlankCurtain
- kind: code
  role: implementation
  target: server/services/presentations.ts#setAudienceBlanked
- kind: doc
  role: intent
  target: docs/requirements/REQ109.md
---

# Blank shared screen

An organizer blanks the screen the room looks at together, without stopping anything else.
