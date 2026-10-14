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
  target: src/api.ts#claimLocalPresentations
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: code
  role: implementation
  target: server/services/presentations.ts#claimOwnership
---

# Sign in

A person with an account signs in with their email address and password.
