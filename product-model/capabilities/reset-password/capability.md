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
- kind: code
  role: implementation
  target: server/emails/password-reset.tsx
---

# Reset password

A person who forgot their password asks for a reset link by email and chooses a new password.
