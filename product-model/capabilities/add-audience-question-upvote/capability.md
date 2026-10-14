---
availability:
- place: web::audience
domain: q-and-a
references:
- kind: code
  role: implementation
  target: src/components/QAPanel.tsx#QAQuestionList
- kind: code
  role: implementation
  target: server/services/presentations.ts#upvoteQuestion
---

# Add audience question upvote

A participant upvotes another participant's question.
