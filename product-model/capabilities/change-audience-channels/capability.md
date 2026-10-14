---
availability:
- place: web::studio
domain: audience-channels
references:
- kind: code
  role: implementation
  target: src/components/ChatPanel.tsx#ChatChannelControl
- kind: code
  role: implementation
  target: src/components/ReactionBar.tsx#ReactionChannelControl
- kind: code
  role: implementation
  target: server/services/presentations.ts#setParticipantChannels
---

# Change audience channels

An organizer opens or closes the room's reactions and live chat.
