---
name: focus-board
description: Conventions for maintaining a personal Logseq-backed Focus Board repository (journals, 5-bucket Focus page, work-item pages, and agent handoff). Load when reading, updating, triaging, or bootstrapping a user's Focus Board.
---

# Focus Board

A Focus Board is a plain-Markdown Logseq graph in git shared by the human and agents to maintain a calm overview of work. Work and personal life use separate repositories with the same layout; check agent memory or ask the user for the repository path.

## Structure

- **Journal-first (`journals/YYYY-MM-DD.md`)**: daily capture and activity log; link to topic pages after the fact as relationships emerge.
- **Work-item pages (`pages/*.md`)**: create only when an item spans more than one day or needs persistent context.
- **Focus page (`pages/Focus.md`)**: five buckets — **Now** (max 1), **Today** (max 3, each with a `why`), **Energizer** (enjoyable-and-important non-top-priority work to avoid burnout), **Waiting** (ball with someone else), and **Parked** (out of sight).

## Conventions

- **Task markers**: map to ball-ownership — `DOING` (active), `TODO` (open), `WAITING` (ball elsewhere; fades unless revisited), `DONE` (finished).
- **Page properties**: `type` (`work-item` | `topic` | `dashboard` | `reference`), `alias` (comma-separated short or external tracker IDs without `#`, so `#id` and `[[Page]]` resolve to one node), `bucket` (`now` | `today` | `energizer` | `waiting` | `parked` | `done`, or the user's language equivalent), `why`, `ref` / `ref-url` (external tracker reference, if any), `agents` (`[[AgentName]]` for resume context), `waiting-on`.
- **Agent inbox**: journal entries referencing `[[<YourAgentName>]]` or `#inbox` are candidates to enrich, link, or triage.
- **Editing safely**: Logseq auto-saves to disk; check `git status` before writing, keep edits surgical, and never commit the user's unrelated in-progress edits.

## Bootstrapping

Load `references/bootstrap.md` when creating a new Focus Board repository.
