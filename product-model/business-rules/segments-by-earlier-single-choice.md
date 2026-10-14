---
appliesTo:
- type: entity
  id: slide
- type: capability
  id: segment-results
references:
- kind: code
  role: implementation
  target: server/segmentation.ts#SEGMENT_REFUSAL_REASONS
---

# A tally is segmented only by an earlier single-choice slide

The slide that groups a tally comes earlier in the presentation and takes one choice from a fixed set: a single-choice Multiple Choice slide, or a quiz question answered by picking.
