---
appliesTo:
- type: entity
  id: presentation
- type: capability
  id: join-presentation
- type: capability
  id: create-presentation
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#createPresentation
---

# Every presentation has its own six-digit join code

A presentation gets a join code no other presentation has when it is created, and keeps it through every session and reset.
