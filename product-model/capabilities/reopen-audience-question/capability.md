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
---

# Reopen audience question

An organizer puts an answered question back in the queue.
