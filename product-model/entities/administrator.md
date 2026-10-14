---
kind: person
acts: external
relations:
- entity: account
  verb: has
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: server/admins.ts
- kind: doc
  role: intent
  target: docs/deployment.md
---

# Administrator

A person who operates the omul instance, signed in with an account whose email the deployment names as an administrator's.
