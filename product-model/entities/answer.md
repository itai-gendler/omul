---
domain: participation
references:
- kind: code
  role: implementation
  target: server/schemas.ts#StoredVoteSchema
- kind: code
  role: implementation
  target: server/services/presentations.ts#submitVote
---

# Answer

What one participant submitted to one slide: a choice, a word, a written answer, a rating, a placement, a split of points, a guess, a pin or a filled-in form.

## Information kept

- **Value** — what the participant chose, wrote, rated, placed, guessed or filled in
- **Statement** — the scale statement or grid item it rates, on a slide that has several
- **Skipped** — whether the participant skipped that statement or item
- **Submitted at** — when it was submitted
- **Upvoters** — the participants who upvoted it, on an Open Text slide that allows upvotes
