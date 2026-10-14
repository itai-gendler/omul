---
availability:
- place: web::studio
domain: q-and-a
references:
- kind: code
  role: implementation
  target: src/components/QAPanel.tsx#QAQuestionList
- kind: code
  role: implementation
  target: server/services/presentations.ts#setQuestionAnswered
- kind: doc
  role: intent
  target: docs/requirements/REQ060.md
---

# Mark audience question answered

An organizer marks a question from the room answered.
