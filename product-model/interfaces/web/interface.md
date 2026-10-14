---
type: web
actors:
- organizer
- participant
- results-viewer
- administrator
entryPoints:
- web: /app
- web: /join/{code}
- web: /present/{id}
- web: /edit/{id}
- web: /results/{id}
- web: /templates
- web: /generate
- web: /workspaces
languages:
- en
- de
- fr
- es
- it
- pt
- nl
references:
- kind: code
  role: implementation
  target: src/router.ts#routeForLocation
- kind: code
  role: implementation
  target: src/App.tsx
- kind: doc
  role: context
  target: README.md
---

# omul web app

The browser app: organizers build and present presentations, participants join and take part from their own devices, anyone holding a results link reads the results, and administrators read the feedback sent about omul.

## Intent

Participants join with a 6-digit code on any device. No accounts needed.
