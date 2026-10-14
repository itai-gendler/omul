---
appliesTo:
- type: entity
  id: presentation
  facts:
  - Ask for names
- type: capability
  id: state-participant-name
- type: capability
  id: submit-answer
references:
- kind: code
  role: implementation
  target: server/schemas.ts#PARTICIPANT_NAME_MAX_LENGTH
- kind: doc
  role: intent
  target: docs/requirements/REQ076.md
---

# On a presentation that asks for names, a participant names themselves before taking part

Participants on such a presentation give a name of up to 80 characters before they answer, and it is kept with what they submit on that presentation.
