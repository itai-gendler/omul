---
appliesTo:
- type: entity
  id: answer
- type: capability
  id: segment-results
references:
- kind: code
  role: implementation
  target: server/segmentation.ts#SEGMENT_MIN_RESPONDENTS
---

# A segment of fewer than five people is held back from readers who cannot edit

A breakdown shown to someone who cannot edit the presentation holds back every group under five people together with at least one other group, shows no head count for them, and is withheld entirely for slides whose answers identify individuals.
