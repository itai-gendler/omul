---
actors:
- participant
access: public
entryPoints:
- web: /join/{code}
- web: /app#join
references:
- kind: code
  role: implementation
  target: src/pages/ParticipantPage.tsx#ParticipantPage
---

# Audience

Where participants join a presentation and take part in it from their own device.
