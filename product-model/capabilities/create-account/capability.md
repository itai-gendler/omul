---
availability:
- place: web::studio
domain: account
references:
- kind: code
  role: implementation
  target: src/auth.tsx#AuthControls
- kind: code
  role: implementation
  target: server/accounts.ts#createAuth
---

# Create account

A person signs up with an email address and a password and is signed in straight away.
