---
stage: register
owner: idea-focus-review
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: 05-frame.md@<rev>, 20-register-draft.md@<rev>
contract: register/1
track: focus
outcome: <go | go-with-conditions | stop>
next: <maquette | build | —>
---

# Register <code>: <project title>

_Result of idea-focus-review and **contract register/1** — the handover of the focus track to maquette or build. Self-contained: the next stage reads only this file. The committee examined the project as a whole (V1–V10, no index — one project, nothing to rank), decided every conflict and K.o. question, and set a priority on every item. Nothing disappears: what is not in the register is under Out of scope with a reason._

## Frame

<!-- 05-frame.md verbatim (all sections except Notes (human)), with its revision. -->

<…>

## Session

- **Committee:** <roles, anonymised> · **Writer:** <role>
- **Date:** <YYYY-MM-DD>
- **Sessions behind this register:** <code>-S01 … <code>-S<nn> · **Contributions:** <n> · **Perspectives heard:** <codes>

## Project check

<!-- One row per field, for the project as a whole. Light green | yellow | red (or unknown); every light names the register items it rests on. Origin: proposed | confirmed | corrected. V7 has two lights (damage / verifiability). -->

| Field | Light | Evidence | Items | Committee note |
| --- | --- | --- | --- | --- |
| V1 Value mechanism & lead KPI | <…> | [estimated] | <R-…> | <…> |
| V2 Value volume | <…> | <…> | <…> | <…> |
| V3 Data situation & preparation · K.o. | <…> | <…> | <…> | <…> |
| V4 Solution pattern & maturity | <…> | <…> | <…> | <…> |
| V5 System character & learning loop | <…> | <…> | <…> | <…> |
| V6 Effort class & operation · K.o. | <…> | <…> | <…> | <…> |
| V7 Damage / verifiability | <… / …> | <…> | <…> | <…> |
| V8 Legal screening · K.o. | <…> | <…> | <…> | <…> |
| V9 Ownership, strategy & adoption · K.o. | <…> | <…> | <…> | <…> |
| V10 Alternative & next test | <…> | <…> | <…> | <…> |

**K.o. decisions** — one line per gate and per K.o. candidate of the draft:

- **<V8> · <R-n>:** <pass | pass with condition: <condition> → <R-m> (MUST, origin review) | fail: <resolution condition>>

- **Outcome:** <go | go with conditions | stop> — <one sentence>
- **Drivers pro:** <…> · **Drivers contra:** <…> · **What would tip it:** <the one assumption that would reverse the outcome>
- **Riskiest assumption (project):** <…>
- **Dissent:** <anonymised, or "none">

## Register

<!-- Every item of the draft that stays in scope, plus the conditions the review added. Sorted MUST → SHOULD → COULD, then by item number. Priority is the committee's decision. Origin: contribution | review. Item numbers are never changed; downstream stages cite them (maquette coverage, build trace R-n → F-<FEAT>-n). -->

| Item | Priority | Type | Statement | Perspectives | Sources | Measure | Touchpoint | Origin |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| R-<n> | <MUST, SHOULD or COULD> | <type> | <…> | <codes> | <C-IDs> | <… or —> | <— or touchpoint> | <contribution or review> |

## Decided conflicts

<!-- Every conflict of the draft. Decision: view A | view B | both as variants (touchpoint) | open question for the next stage. Otherwise: "no conflicts". -->

| Item | Decision | Reason |
| --- | --- | --- |
| R-<n> | <…> | <one sentence> |

## Glossary

<!-- From the draft, confirmed. -->

| Terms used | Preferred term |
| --- | --- |
| <…> | <…> |

## Open questions

<!-- Items of type question, conflicts left open, conditions still to verify. The next stage turns them into its OQ-n and never re-asks them as new. -->

| # | Question | Items | Who can answer |
| --- | --- | --- | --- |
| 1 | <…> | <R-…> | <role> |

## Out of scope

<!-- From the draft, plus items the committee set to "won't" (with reason). Nothing disappears. -->

| Item or contribution | Statement | Reason | Forward to / revisit when |
| --- | --- | --- | --- |
| <…> | <…> | <won't: … | outside scope: …> | <…> |

## Handover

- **Next stage:** <maquette | build | — (outcome stop)>
- **Demo focus:** <the R-IDs a maquette must show — usually a few MUST items; "—" when next is build>
- **Sponsor:** <who decides after the next stage>
- **Decision date:** <YYYY-MM-DD | open>
- **Open before or during the next stage:** <…>
- **Coverage:** every contribution of the sessions above is in an item or under Out of scope — see `20-register-draft.md@<rev>`.

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
