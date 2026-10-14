---
entities:
- entity: presentation
  collects:
  - Join code
entryPoints:
- web: /app#join
references:
- kind: code
  role: implementation
  target: src/pages/JoinPage.tsx#JoinPage
---

# Join

Where a participant enters a presentation's six-digit code or scans its QR code.
