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

# Remove audience question upvote

A participant takes back their upvote on a question.
