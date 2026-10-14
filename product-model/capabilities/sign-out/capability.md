---
availability:
- place: web::signed-in
domain: account
references:
- kind: code
  role: implementation
  target: src/auth.tsx#AuthControls
---

# Sign out

A signed-in person ends their session in this browser.
