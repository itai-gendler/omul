---
actors:
- organizer
access: public
entryPoints:
- web: /app
- web: /edit/{id}
- web: /present/{id}
- web: /preview/{id}
references:
- kind: code
  role: implementation
  target: src/pages/HomePage.tsx#HomePage
---

# Studio

Where an organizer builds, previews and presents presentations. Everything here works without an account; signing in adds ownership, sharing and comments.
