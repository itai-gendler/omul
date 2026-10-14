---
entities:
- entity: presentation
  shows:
  - Title
  - Results visibility
- entity: slide
  shows:
  - Type
  - Question
  - Options
  - Correct answers
  - Content
  - Presenter notes
entryPoints:
- web: /preview/{id}
references:
- kind: code
  role: implementation
  target: src/pages/PreviewPage.tsx#PreviewPage
---

# Preview

A dry run of a presentation, with generated test answers, showing what the presenter and the room would see.
