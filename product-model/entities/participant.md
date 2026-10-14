---
kind: person
acts: external
relations:
- entity: answer
  verb: gives
  cardinality: one-to-many
- entity: audience-question
  verb: asks
  cardinality: one-to-many
- entity: chat-message
  verb: sends
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/api.ts#getParticipantId
- kind: code
  role: implementation
  target: server/services/participant-names.ts
---

# Participant

A member of the audience who joins a presentation with its six-digit code, on any device and without an account. A participant is told apart by the device they take part from.

## Information kept

- **Name** — what they said they are called, on a presentation that asks for names
