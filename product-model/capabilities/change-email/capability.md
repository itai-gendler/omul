---
availability:
- place: web::signed-in
- place: web::studio
domain: account
references:
- kind: code
  role: implementation
  target: src/auth.tsx#AuthControls
- kind: code
  role: implementation
  target: server/accounts.ts#createAuth
- kind: code
  role: implementation
  target: server/emails/change-email.tsx
---

# Change email

A signed-in person moves their account to another email address, confirmed from both addresses.
