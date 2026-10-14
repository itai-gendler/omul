---
references:
- kind: code
  role: implementation
  target: server/schemas.ts#StoredSlideCommentSchema
- kind: code
  role: implementation
  target: server/services/slide-comments.ts#addSlideComment
---

# Slide comment

A comment an account with access to a presentation writes on one of its slides.

## Information kept

- **Body** — what was written, up to 2,000 characters
- **Author name** — the display name of the account that wrote it
- **Written at** — when it was written
