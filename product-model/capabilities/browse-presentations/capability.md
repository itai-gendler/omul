---
availability:
- place: web::studio
- place: cli
domain: presentations
references:
- kind: code
  role: implementation
  target: src/pages/HomePage.tsx#HomePage
- kind: code
  role: implementation
  target: src/api.ts#listMyPresentations
- kind: code
  role: implementation
  target: src/api.ts#listSharedPresentations
- kind: code
  role: implementation
  target: cli/commands.ts#runCommand
---

# Browse presentations

An organizer sees their presentations: those this browser holds the edit link of, those their account owns, and those shared with them.
