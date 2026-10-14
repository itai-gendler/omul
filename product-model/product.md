---
id: omul
summary: 'Self-hosted live interactive presentations: polls, word clouds, Q&A, scales, rankings, quizzes and leaderboards that participants join with a six-digit code.'
category: audience-engagement
tags:
- live-polling
- presentations
- quizzes
- q-and-a
- self-hosted
authors:
- name: Enrico Scherlies
license: AGPL-3.0-only
languages:
- en
- de
- fr
- es
- it
- pt
- nl
limitations:
- Participants take part without an account; a participant is told apart only by the device they join from.
- Reactions cross the shared screen as they happen and are never kept.
- Drafting a presentation from a prompt is the only behavior that calls an outside service, and only the prompt is sent.
- Presentations are shared, and workspace members added, only with accounts already registered on the instance; omul sends no invitations.
---

# omul

omul runs live interactive presentations on a server its operator hosts. An organizer builds a presentation of
question slides — Multiple Choice, Word Cloud, Open Text, Scale, Ranking, 2x2 Grid, 100 Points, Guess the Number,
Pin on Image, Quiz and Form — with leaderboards and content slides between them, then presents it. The room joins
from any device with a six-digit code, a link or a QR code, answers each slide, asks questions, reacts and chats,
and sees the tallies when the organizer's reveal mode allows. Organizers can work without an account, holding a
private edit link; with one they own presentations, share them with other accounts, comment on slides and work in
workspaces their team owns. Results are followed live, exported as a spreadsheet or PDF, and shared through a
revocable read-only link. A command-line client creates presentations and reads their results with a personal API key.

## Intent

"Self-hosted live interactive presentations — polls, word clouds, Q&A, scales, rankings, 2x2 grids, 100-point
splits, number guesses, quizzes and leaderboards. Participants join with a 6-digit code on any device. No accounts
needed." The product runs as one container with no third-party runtime host; the one deliberate exception is
drafting a deck from a prompt, which is off unless the operator configures it, and from which "only the prompt
leaves. Your decks, your participants' answers and your session data are never sent anywhere."
