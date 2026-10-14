---
domain: q-and-a
references:
- kind: code
  role: implementation
  target: server/schemas.ts#StoredQAQuestionSchema
- kind: code
  role: implementation
  target: server/services/presentations.ts#submitQuestion
---

# Audience question

A question a participant sends through the presentation's Q&A.

## Information kept

- **Text** — what was asked
- **Asked at** — when it was asked
- **Upvoters** — the participants who upvoted it
- **Answered at** — when the presenter marked it answered

## States

### Open

In the queue, waiting to be answered.

### Awaiting approval

Sent to a presentation whose questions wait for approval; only the presenter's side sees it.

### Answered

Marked answered by the presenter.
