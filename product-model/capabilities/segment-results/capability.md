---
availability:
- place: web::shared-results
domain: results
references:
- kind: code
  role: implementation
  target: src/components/SegmentedResults.tsx#SegmentedResults
- kind: code
  role: implementation
  target: server/services/presentations.ts#getSegmentedResults
- kind: code
  role: implementation
  target: server/segmentation.ts#segmentDisclosure
- kind: doc
  role: intent
  target: docs/requirements/REQ020.md
---

# Segment results

On the results page, a slide's tally is split by what the same participants chose on an earlier single-choice slide.
