---
domain: account
relations:
- entity: api-key
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/accounts.ts#createAuth
- kind: code
  role: implementation
  target: src/auth.tsx#AuthControls
---

# Account

The sign-in identity of a person who uses omul with an account.

## Information kept

- **Name** — the display name collaborators and workspace members see
- **Email** — the address they sign in with and receive mail at
- **Password** — the secret they sign in with, at least eight characters
- **Email verified** — whether they have followed the verification link sent to their address
