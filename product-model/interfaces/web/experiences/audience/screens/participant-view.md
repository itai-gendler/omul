---
entities:
- entity: presentation
  shows:
  - Title
  - Pace
  - Language
  - Current slide
  - Q&A visibility
  - Theme
  - Logo
- entity: slide
  shows:
  - Type
  - Question
  - Options
  - Correct answers
  - Content
  - Items
  - Scale
  - Grid axes
  - Guess range
  - Target area
  - Form fields
  - Time limit
  - Answer upvoting
- entity: answer
  shows:
  - Value
  - Upvoters
  collects:
  - Value
- entity: audience-question
  shows:
  - Text
  - Upvoters
  collects:
  - Text
- entity: chat-message
  shows:
  - Text
  - Sent at
  collects:
  - Text
- entity: participant
  shows:
  - Name
  collects:
  - Name
- entity: participant-feedback
  collects:
  - Rating
  - Comment
entryPoints:
- web: /join/{code}
references:
- kind: code
  role: implementation
  target: src/pages/ParticipantPage.tsx#ParticipantPage
- kind: code
  role: implementation
  target: src/components/ParticipantSlideView.tsx#ParticipantSlideView
---

# Participant view

A participant's own view of a presentation: the slide in front of the room, the control to answer it, and the Q&A, reactions and chat the presentation offers.
