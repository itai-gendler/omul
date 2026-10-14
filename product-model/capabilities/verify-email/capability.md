---
availability:
- place: web::studio
domain: account
references:
- kind: code
  role: implementation
  target: src/auth.tsx#VerifyEmailBanner
- kind: code
  role: implementation
  target: server/accounts.ts#createAuth
---

# Verify email

A person confirms their email address by following the link omul sent to it.
