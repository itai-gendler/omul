---
entities:
- entity: presentation
  shows:
  - Title
- entity: slide
  shows:
  - Type
  - Question
  - Options
- entity: answer
  shows:
  - Value
entryPoints:
- web: /results/{id}
references:
- kind: code
  role: implementation
  target: src/pages/SharedResultsPage.tsx#SharedResultsPage
- kind: code
  role: implementation
  target: src/components/SegmentedResults.tsx#SegmentedResults
---

# Results

One presentation's results, slide by slide, read-only.
