---
availability:
- place: web::audience
domain: q-and-a
references:
- kind: code
  role: implementation
  target: src/components/QAPanel.tsx#QAComposer
- kind: code
  role: implementation
  target: server/services/presentations.ts#submitQuestion
- kind: doc
  role: intent
  target: docs/requirements/REQ035.md
---

# Ask question

A participant sends a question through the presentation's Q&A.
