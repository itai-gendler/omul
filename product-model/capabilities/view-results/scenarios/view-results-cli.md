---
kind: primary
routes:
  cli: Command line
steps:
- text: The Organizer runs omul results with the presentation's id
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    cli:
      place: cli
- text: The client prints each Slide's tally; with --json it prints the full tally
  kind: product
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  - entity: answer
    effect: reads
    facts:
    - Value
  contexts:
    cli:
      place: cli
---

# Read results on the command line

## Trigger

The Organizer collects results into a report.

## Outcome

The Organizer has the tallies without opening a browser.
