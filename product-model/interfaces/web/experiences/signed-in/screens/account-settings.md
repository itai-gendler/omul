---
entities:
- entity: account
  shows:
  - Name
  - Email
  - Email verified
  collects:
  - Email
  - Password
- entity: api-key
  shows:
  - Name
  - Key
  - Created at
  collects:
  - Name
references:
- kind: code
  role: implementation
  target: src/auth.tsx#AuthControls
---

# Account settings

The signed-in person's own account: their email, their API keys and deleting the account.
