---
entities:
- entity: presentation
  shows: &id001
  - Title
  - Pace
  - Language
  - Results visibility
  - Q&A enabled
  - Q&A visibility
  - Reactions enabled
  - Chat enabled
  - Ask for names
  - Theme
  - Own theme
  - Logo
  collects: *id001
- entity: slide
  shows: &id002
  - Type
  - Question
  - Options
  - Correct answers
  - Content
  - Position
  - Selection limit
  - Response cap
  - Answer upvoting
  - Items
  - Scale
  - Skipping allowed
  - Grid axes
  - Guess range
  - Target area
  - Form fields
  - Quiz answer mode
  - Time limit
  - Leaderboard size
  - Result display
  - Results visibility
  - Appearance
  - Presenter notes
  collects: *id002
- entity: slide-comment
  shows:
  - Body
  - Author name
  - Written at
  collects:
  - Body
entryPoints:
- web: /edit/{id}
- web: /app#create
references:
- kind: code
  role: implementation
  target: src/pages/CreatePage.tsx#CreatePage
- kind: code
  role: implementation
  target: src/components/SlideEditor.tsx#SlideEditor
---

# Editor

Where a presentation and its slides are written: its settings, each slide's question, options and settings, and the comments on each slide.
