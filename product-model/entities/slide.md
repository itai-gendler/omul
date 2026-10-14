---
relations:
- entity: answer
  verb: receives
  cardinality: one-to-many
- entity: slide-comment
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/schemas.ts#SlideSchema
- kind: code
  role: implementation
  target: server/schemas.ts#SLIDE_TYPE_LABELS
---

# Slide

One step of a presentation: a question the room answers, a leaderboard, or content the room reads.

## Information kept

- **Type** — Multiple Choice, Word Cloud, Open Text, Scale, Ranking, 2x2 Grid, 100 Points, Guess the Number, Pin on Image, Quiz, Form, Leaderboard, Text, Image, Video, Embedded Deck or How to Join
- **Question** — the question or heading the room reads
- **Options** — the choices of a Multiple Choice or Quiz slide
- **Correct answers** — which options are correct, or the typed answers a quiz question accepts
- **Content** — the text, image, video or embedded deck a content slide shows, with its description
- **Position** — where it sits in the presentation's order
- **Selection limit** — how many options one participant may choose
- **Response cap** — how many answers one participant may give on a Word Cloud or Open Text slide
- **Answer upvoting** — whether the room may upvote Open Text answers
- **Items** — the statements, ranking items, grid items or point items the room rates, orders, places or splits points across
- **Scale** — the bounds and labels of a scale
- **Skipping allowed** — whether a participant may skip a statement or a grid item
- **Grid axes** — the titles and end labels of a 2x2 Grid's two axes
- **Guess range** — the range, step, reference value and tolerance of a Guess the Number slide
- **Target area** — the image and the target area of a Pin on Image slide
- **Form fields** — the fields of a Form slide, each text, email or choice, and whether each is required
- **Quiz answer mode** — whether a quiz question is answered by choosing an option or by typing
- **Time limit** — how long a quiz question stays open
- **Leaderboard size** — how many places a Leaderboard slide shows
- **Result display** — how the tally is drawn: chart style, counts or percentages, and the layout of written answers
- **Results visibility** — this slide's own reveal mode, or the presentation's
- **Appearance** — layout, text size, background and colors
- **Presenter notes** — notes only the presenter's side sees
