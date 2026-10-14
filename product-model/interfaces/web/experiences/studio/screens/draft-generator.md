---
entities:
- entity: deployment-settings
  shows:
  - Drafting provider
  - Anonymous drafting
entryPoints:
- web: /generate
references:
- kind: code
  role: implementation
  target: src/pages/GeneratePage.tsx#GeneratePage
---

# Generate a deck

Where an organizer describes a session and gets a draft presentation to edit.
