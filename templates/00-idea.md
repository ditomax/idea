---
stage: control
owner: idea
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: —
# --- only in 00-idea.md ---
org: <organisation or department>
code: <2–4 letters, prefixes every card ID, e.g. PMK>
language: en                 # language of the result files' content
git: no                      # yes | no — checked by the Director at start
profile: none                # none | profile/ (if a profile folder exists)
budget_min: {collect: 45, evaluate: 30, shortlist: 30}
---

# Ideas <code>: <org>

<!-- This file belongs to the Director. No other skill writes here. -->

## Context

- **What the department does:** <one or two sentences>
- **Company goals / AI strategy known:** <…, or "not stated" — feeds the strategy-link field>
- **Departments at the interfaces:** <…>

## Cards

<!-- One row per card, in ID order. Status: sketch | done (evaluation-ready). Evaluation: — | in_progress | done | stale | parked. Never delete a row; a merged or rejected card keeps its row with the decision in the last column. -->

| ID | Title | Status | Origin | Evaluation | Note |
| --- | --- | --- | --- | --- | --- |
| <code>-001 | <…> | sketch | own idea | — | |

**Next ID:** <code>-<nnn>

## Shortlist

- **Current:** <— | 10-shortlist.md@<rev> (done <date>) | 10-shortlist.v2.md …>
- **Committee round:** <n>

## Imports

<!-- One row per foreign format, so the next import of the same format needs no questions. -->

| Format | Mapping (column → card field) | First used | Cards |
| --- | --- | --- | --- |
| <e.g. xlsx-12col> | <see idea-collect known formats, or the mapping agreed with the user> | <date> | <IDs> |

## Sessions

<!-- Appended by the Director: one line per session. -->

| Date | Stage | Mode | Minutes | Result | Decision |
| --- | --- | --- | --- | --- | --- |
| <date> | start | — | — | workspace created | — |

## Parked / open

<!-- Threads not finished, stations skipped, ideas parked with consent. The next session resumes here. Off-record content is never listed. -->

- <…>

## Open items for the Director

- <budget overruns, corrections that clustered on one field, anything for the retro>

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
