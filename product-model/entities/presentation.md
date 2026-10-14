---
relations:
- entity: slide
  verb: has
  cardinality: one-to-many
- entity: collaborator
  verb: has
  cardinality: one-to-many
- entity: audience-question
  verb: has
  cardinality: one-to-many
- entity: chat-message
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/schemas.ts#StoredPresentationSchema
- kind: code
  role: implementation
  target: server/services/presentations.ts#createPresentation
---

# Presentation

A deck of slides the organizer runs live: the questions the room answers, the content between them and the settings that decide how the room takes part.

## Information kept

- **Title** — the name of the presentation
- **Join code** — the six-digit code participants enter to join
- **Pace** — Presenter pace, where the room follows the slide the presenter shows, or Audience pace, where each participant moves through the slides themselves
- **Language** — the language participant screens use: English, German, French, Spanish, Italian, Portuguese or Dutch
- **Results visibility** — when a tally reaches the room: Instant, On click or Private
- **Current slide** — the slide the presenter is showing
- **Slide opened at** — when each slide was first shown in the session, which starts a quiz question's answer window
- **Revealed slides** — the slides whose tally the presenter has revealed
- **Closed slides** — the slides the presenter has closed to submissions
- **Screen blanked** — whether the shared screen is blanked
- **Session started at** — when the current session went live
- **Session ended at** — when the session ended
- **Q&A enabled** — whether the room may send questions
- **Q&A visibility** — who reads the room's questions: Only the presenter or Everyone
- **Q&A approval** — whether each question waits for approval before the room sees it
- **Reactions enabled** — whether the room may send reactions
- **Chat enabled** — whether the room may write in the chat
- **Ask for names** — whether participants must say their name before taking part
- **Join bar shown** — whether the shared screen shows the join code, link and QR code
- **Theme** — one of the built-in themes, or the presentation's own theme
- **Own theme** — the colors and font of the presentation's own theme
- **Logo** — the logo image shown on the presentation's screens, with its description
- **Edit link** — the private link that lets whoever holds it edit and run the presentation without an account
- **Results link** — the read-only link to the presentation's results, while one exists
- **Results link created at** — when the current results link was created
- **Owner** — the account that owns it, when no workspace does
- **Workspace** — the workspace that owns it, when one does
- **Created at** — when it was created

## States

### Draft

Being prepared. The room can join and wait; an audience-paced presentation already takes answers.

### Live

Being presented. The room takes part in the slide in front of it.

### Ended

Finished. Nothing more is taken, and the room is told the presentation ended.
