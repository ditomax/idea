---
stage: control
owner: idea
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: —
# --- only in 00-idea.md ---
track: focus                 # explore | focus — set once at the first call, never changed in this workspace
org: <organisation or department>
code: <2–4 letters, prefixes every session and contribution ID, e.g. IMP>
language: en                 # language of the result files' content
git: no                      # yes | no — checked by the Director at start
profile: none                # none | profile/ (if a profile folder exists)
budget_min: {session: 45, consolidate: 30, review: 60}
---

# Focus <code>: <project title>

<!-- This file belongs to the Director. No other skill writes here. Track focus: one fixed project, contributions from many perspectives, one register. -->

## Frame

- **Current:** <— | 05-frame.md@<rev> (done <date>)>

## Sessions

<!-- One row per session file (interview, collector debrief or import of a mail return), in ID order. Status: in_progress | done | stale. Never delete a row. After a redo "current: <file>@<rev>" in Note. -->

| Session | Perspective(s) | Date | Mode | Contributions | Status | Note |
| --- | --- | --- | --- | --- | --- | --- |
| <code>-S01 | <ANM> | <date> | interview | <code>-C001 … <code>-C012 | done | |

**Next session:** <code>-S<nn> · **Next contribution:** <code>-C<nnn>

## Register

- **Draft:** <— | 20-register-draft.md@<rev> (<status>)>
- **Register:** <— | 10-register.md@<rev> (done <date>) | 10-register.v2.md …>
- **Outcome:** <— | go | go with conditions | stop>

## Imports

<!-- One row per return format, so the next import of the same format needs no questions. -->

| Format | Mapping | First used | Sessions |
| --- | --- | --- | --- |
| <e.g. md-contributions, md-card> | <see idea-focus-collect known formats, or the mapping agreed with the user> | <date> | <IDs> |

## Log

<!-- Appended by the Director: one line per stage run. -->

| Date | Stage | Mode | Minutes | Result | Decision |
| --- | --- | --- | --- | --- | --- |
| <date> | start | — | — | workspace created (track focus) | — |

## Parked / open

<!-- Perspectives not yet heard, threads not finished. Off-record content is never listed. -->

- <…>

## Open items for the Director

- <budget overruns, corrections that clustered, anything for the retro>

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
