---
availability:
- place: web::audience
- place: web::studio
domain: audience-channels
references:
- kind: code
  role: implementation
  target: src/components/ChatPanel.tsx#ChatComposer
- kind: code
  role: implementation
  target: server/services/presentations.ts#postChatMessage
- kind: doc
  role: intent
  target: docs/requirements/REQ078.md
---

# Post chat message

A participant, or the presenter's side, writes in the presentation's live chat.
