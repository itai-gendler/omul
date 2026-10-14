---
availability:
- place: web::signed-in
domain: account
references:
- kind: code
  role: implementation
  target: src/auth.tsx#AuthControls
---

# Revoke API key

A signed-in person revokes one of their personal keys.
