---
entities:
- entity: presentation
  shows:
  - Title
  - Join code
  - Current slide
  - Revealed slides
  - Closed slides
  - Screen blanked
  - Join bar shown
  - Q&A enabled
  - Q&A visibility
  - Q&A approval
  - Reactions enabled
  - Chat enabled
  - Edit link
  - Results link
  - Results link created at
  - Session started at
  collects:
  - Q&A enabled
  - Q&A visibility
  - Q&A approval
  - Reactions enabled
  - Chat enabled
- entity: slide
  shows:
  - Type
  - Question
  - Options
  - Correct answers
  - Content
  - Time limit
  - Leaderboard size
  - Result display
  - Presenter notes
- entity: answer
  shows:
  - Value
  - Upvoters
- entity: audience-question
  shows:
  - Text
  - Upvoters
  - Answered at
- entity: chat-message
  shows:
  - Text
  - Sent at
  collects:
  - Text
- entity: participant
  shows:
  - Name
- entity: slide-comment
  shows:
  - Body
  - Author name
  - Written at
  collects:
  - Body
entryPoints:
- web: /present/{id}
references:
- kind: code
  role: implementation
  target: src/pages/PresenterPage.tsx#PresenterPage
- kind: code
  role: implementation
  target: src/components/PresenterSlideView.tsx#PresenterSlideView
---

# Presenter view

The screen an organizer runs a presentation from and projects to the room: the current slide and its live tally, the join code, and the panels for questions, chat, participants, comments and notes.
