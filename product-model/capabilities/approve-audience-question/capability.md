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
  target: server/services/presentations.ts#approveQuestion
- kind: doc
  role: intent
  target: docs/requirements/REQ038.md
---

# Approve audience question

An organizer publishes a question that waits for approval to the room.
