---
stage: shortlist
owner: idea-evaluate
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: cards/<ID>-card.md@<rev>, evaluations/<ID>-eval.md@<rev>, …   # every ranked card AND its evaluation, paths relative to the work folder
contract: H1/2               # handover contract version; H1/2 read by maquette ≥ 0.6.0 (older maquette reads it as H1/1 and ignores the additions)
next_maquette: <ID>          # the entry the committee sends into the next maquette — exactly one ID, or "open"
---

# Shortlist <org code>: <session title or date>

_Result of idea-evaluate and **contract H1** to maquette. Each entry is self-contained: the maquette Director reads only this file, proposes the entry named under "Maquette order" (the user confirms or picks another — exactly one), and sparring prefills from that entry. Ideas never disappear: what is not on the shortlist is under "Parked / rejected" with a reason._

## Maquette order

<!-- Decided by the committee at the close (question S7). This is the instruction to maquette: which entry is built next, and — for an umbrella entry — which variant(s) the demo shows. Must match `next_maquette` in the frontmatter. -->

- **Next maquette:** <ID — title | open (reason)>
- **Demo variant(s):** <only for an umbrella entry: variant IDs the demo shows, in order; otherwise "—">
- **Later:** <further entries or variants in the intended order, or "by rank">

## Session

- **Committee:** <roles, anonymised; e.g. "Head of Product Marketing, IT lead, Managing Director">
- **Writer:** <the one person at the keyboard>
- **Date:** <YYYY-MM-DD>
- **Cards evaluated:** <IDs>
- **Method:** Kriterienkatalog Konzeptbewertung v0.3 — ten fields V1–V10, K.o. gates V3, V6, V8, V9; lights green 5 / yellow 3 / red 1; index = round(W × M × R); confidence from the evidence marks. Full evaluations in `evaluations/<ID>-eval.md`.

## Ranking

| Rank | ID | Title | Index | Tendency | Confidence | K.o. gates | Recommendation | Decision |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | <ID> | <…> | <1–25 | provisional | —> | <rather go | conditional | rather no-go | parked | not yet assessable> | <high | medium | low> | <V3 … · V6 … · V8 … · V9 …> | <maquette workshop | maquette discovery | test assumption first | park> | <go | test first | park (revisit: …) | reject> |

<!-- Recommendation = what the index and the rules suggest; Decision = what the committee decided, with a reason in the rationale below. A shortlisted entry the committee parks stays in this table with `park (revisit: <condition or date>)` — the "Parked / rejected" table below is for ideas that did not make the shortlist. -->

<!-- Sorted by the committee's decision, not by the arithmetic alone. If the order deviates from the index, the rationale in the entry says why. Indices from different departments and sessions are a rough sorting aid, not a ranking. -->

## Entries

<!-- One complete entry per row of the Ranking table — also for entries the committee parks (decision `park`). A shortlist without entries is not a valid H1 handover: a later committee round or maquette must be able to start from any ranked entry without opening other files. -->

### 1. <ID> — <title>

#### Card

<!-- Verbatim copy of the card's fields (cards/<ID>-card.md). Not a summary — the maquette must not need the card file. -->

- **Status:** <…>
- **Opportunity:** <…>
- **Department(s):** <…>
- **Process & systems:** <…>
- **Cost of the status quo:** <…> [evidenced|estimated|unknown]
- **Stakeholders & needs:** <…>
- **Data situation:** <…> [evidenced|estimated|unknown]
- **Earlier attempts:** <…> [evidenced|estimated|unknown]
- **Personal data:** <…>
- **Legal / ethics / standards:** <…>
- **Strategy link:** <…> [evidenced|estimated|unknown]
- **Riskiest assumption:** <…>
- **Minimum success criterion:** <…>
- **Views:** <…>
- **Origin:** <…>
- **Relation:** <— | consolidated from … | umbrella over … | split from … | variant of <ID> (also on this shortlist: yes/no)>

#### Variants

<!-- Only for an umbrella entry: the card's Variants table verbatim, with each variant's rank on this shortlist (or "not shortlisted"). Otherwise: "not relevant for this entry". -->

| Variant | Title | What differs | Needs only this variant has | Evaluation | Rank here |
| --- | --- | --- | --- | --- | --- |
| <ID> | <…> | <…> | <…> | <…> | <n | not shortlisted> |

#### Evaluation

<!-- Summary of evaluations/<ID>-eval.md — lights, evidence and one note per field. The full reasoning stays in the evaluation file. -->

| Field | Light | Evidence | Origin | Committee note |
| --- | --- | --- | --- | --- |
| V1 Value mechanism & lead KPI | <green|yellow|red> | [evidenced|estimated|unknown] | <proposed|confirmed|corrected> | <…> |
| V2 Value volume | … | … | … | <…> |
| V3 Data situation & preparation effort · K.o. | … | … | … | <…> |
| V4 Solution pattern & maturity | … | … | … | <…> |
| V5 System character & learning loop | … | … | … | <…> |
| V6 Effort class & operation · K.o. | … | … | … | <…> |
| V7 Damage class / verifiability | <…> / <…> | … | … | <two lights> |
| V8 Legal screening · K.o. | … | … | … | <…> |
| V9 Ownership, strategy & adoption · K.o. | … | … | … | <…> |
| V10 Alternative & next test | … | … | … | <…> |

**K.o. gates** — one line each. A gate is never left open: the committee decides it, gives an estimate, or waives it.

<!-- Rule for idea-evaluate: an `[unknown]` in a K.o. field does not send the card back and does not block the ranking. The skill asks the committee, one gate at a time: "Can you estimate this, or is the gate not relevant for this idea?" An estimate enters the arithmetic as `[estimated]` with the estimator's role. A waiver excludes the field from its axis mean and from the confidence rule, and travels into the maquette as an open question. A waiver resolves unknown, never red. Only a confirmed red excludes an idea (parked, with resolution condition). -->

- **V3 data:** <pass | fail | estimate: <light> [estimated] (<who>) | waiver: <reason> (committee, <date>)>
- **V6 effort:** <…>
- **V8 legal:** <…>
- **V9 ownership:** <…>

- **W (value):** <arithmetic> = <…> · **M (feasibility):** <arithmetic> = <…> · **R:** <1.0 | 0.8 | 0.6> · **Index:** **<1–25>** <or "no score — parked" | "provisional — low confidence">
- **Tendency:** <rather go | conditional | rather no-go | parked | not yet assessable> · **Confidence:** <high | medium | low> — <reason>
- **Drivers pro:** <…> · **Drivers contra:** <…> · **What would tip it:** <the one assumption>

**Committee rationale:** <why this rank — two or three sentences in the committee's words>

**Dissent:** <a member's recorded disagreement, anonymised, or "none">

#### Handover to maquette

- **Sponsor:** <name or role — the person who decides after the maquette>
- **Decision date:** <YYYY-MM-DD or "open">
- **Recommended mode:** <workshop | discovery> — <one reason; conditional tendency usually means workshop as the cheapest test>
- **Prefill for sparring:** <!-- Copy this mapping list verbatim — it is a fixed specification, not a summary to rewrite. maquette ≥ 0.4.0 reads these mappings; sparring confirms, never re-asks. -->
  - Q1 demand reality ← Stakeholders & needs, Cost of the status quo
  - Q2 status quo ← Process & systems, Cost of the status quo
  - Q3 the specific person ← Stakeholders & needs (first line = the person)
  - §3 premises ← Data situation, Earlier attempts
  - §5 guardrails ← Personal data, Legal / ethics / standards, waivers above
  - §9 riskiest assumption ← Riskiest assumption; cheapest test ← V10 note
  - Q4 smallest demo ← Minimum success criterion (as a starting point — sparring decides the demo)
  - Field of application ← V4 solution pattern, Process & systems (proposed, sparring confirms)
  - §5 guardrail candidate, §9 "if wrong" ← V7 damage class
  - §3 premise ← "What would tip it"; Views and Dissent → Q1/Q3 hints or §8
  - Q4 demo scenario ← Demo variant(s) under "Maquette order" (umbrella only); other variants → §8 as later scope
- **Open before or during the maquette:** <every `[unknown]` and every waiver, one line each — these become open questions in 10-seed.md §8>

### 2. <ID> — <title>

<!-- same structure -->

## Parked / rejected

<!-- Only cards that are NOT in the Ranking table: evaluated but not ranked, rejected, consumed (merged into / split into), or not evaluated in this round. A ranked entry with decision `park` stays in Ranking and Entries only — never listed here as well. -->

| ID | Title | Decision | Reason | Revisit when |
| --- | --- | --- | --- | --- |
| <ID> | <…> | <parked | rejected | merged into <ID> | split into <IDs>> | <…> | <condition or date, or "—"> |

<!-- Consumed cards (merged into / split into) are listed here with their evaluation marked superseded; they never appear as entries. Variants of an umbrella that were not shortlisted are listed in the umbrella entry's Variants table, not here. -->

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
