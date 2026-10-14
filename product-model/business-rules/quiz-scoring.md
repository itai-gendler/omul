---
appliesTo:
- type: entity
  id: answer
- type: capability
  id: submit-answer
- type: capability
  id: view-results
references:
- kind: code
  role: implementation
  target: server/schemas.ts#QUIZ_CORRECT_POINTS
- kind: code
  role: implementation
  target: server/schemas.ts#QUIZ_SPEED_POINTS
- kind: doc
  role: intent
  target: docs/requirements/REQ056.md
---

# A correct quiz answer scores 500 points plus up to 500 for speed

A correct answer earns 500 points, and up to 500 more on a straight line from the moment the question opens to its deadline; an untimed question awards the 500 for speed in full, and an answer given before the presenter restarted the timer earns no speed points. A wrong answer, or none, scores nothing. Points follow the answer key as it stands, so re-marking the correct options re-scores the room. A leaderboard ranks participants by their points across the presentation's quiz questions.
