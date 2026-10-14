---
availability:
- place: web::signed-in
domain: account
references:
- kind: code
  role: implementation
  target: src/auth.tsx#AuthControls
---

# Create API key

A signed-in person creates a named personal key for the command-line client or the HTTP API.
