---
domain: account
references:
- kind: code
  role: implementation
  target: src/auth.tsx#AuthControls
- kind: code
  role: implementation
  target: cli/config.ts
---

# API key

A personal key an account holder creates to drive omul from the command-line client or the HTTP API.

## Information kept

- **Name** — the label given when it was created
- **Key** — the secret value, shown once when it is created
- **Created at** — when it was created
