---
availability:
- place: web::signed-in
domain: account
references:
- kind: code
  role: implementation
  target: src/auth.tsx#AuthControls
- kind: code
  role: implementation
  target: server/accounts.ts#createAuth
---

# Delete account

A signed-in person permanently deletes their account after confirming their password.
