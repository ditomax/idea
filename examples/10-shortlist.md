---
stage: shortlist
owner: idea-evaluate
status: done
revision: 2
created: 2026-09-15T11:30
updated: 2026-09-15T11:55
input: cards/EXG-001-card.md@4, cards/EXG-002-card.md@3, evaluations/EXG-001-eval.md@3, evaluations/EXG-002-eval.md@2
contract: H1/1
---
<!-- Example — fictitious Example GmbH. Shows what a finished file looks like; not a template. -->

# Shortlist EXG: Sales committee round 2026-09-15

_Result of idea-evaluate and **contract H1** to maquette. Each entry is self-contained: the maquette Director reads only this file, lists the entries by title, lets the user pick exactly one, and sparring prefills from that entry. Ideas never disappear: what is not on the shortlist is under "Parked / rejected" with a reason._

## Session

- **Committee:** Managing Director, Head of Sales, IT lead, Data protection coordinator
- **Writer:** Sales operations coordinator
- **Date:** 2026-09-15
- **Cards evaluated:** EXG-001, EXG-002
- **Method:** Kriterienkatalog Konzeptbewertung v0.3 — ten fields V1–V10, K.o. gates V3, V6, V8, V9; lights green 5 / yellow 3 / red 1; index = round(W × M × R); confidence from the evidence marks. Full evaluations in `evaluations/<ID>-eval.md`.

## Ranking

| Rank | ID | Title | Index | Tendency | Confidence | K.o. gates | Recommendation | Decision |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | EXG-001 | Offer draft assistant | 12 | conditional | medium | V3 estimate · V6 pass · V8 pass · V9 pass | maquette workshop | go |
| 2 | EXG-002 | Service ticket triage | 8 | conditional | medium | V3 pass · V6 pass · V8 pass · V9 pass | park | park (revisit: after the ticket system migration, Q1 2027) |

## Entries

### 1. EXG-001 — Offer draft assistant

#### Card

- **Status:** evaluation-ready
- **Opportunity:** Sales engineers start each offer from a generated draft — customer data, installed pumps and text blocks from earlier offers already filled in — and spend their time on the technical fit.
- **Department(s):** Sales (interface: Inside sales, IT)
- **Process & systems:** Inquiry logged in the CRM → sales engineer finds a similar old offer (Word, shared drive), copies it, replaces customer, pump type, quantities and prices by hand (price list in the ERP), rewrites scope text → inside sales checks the format and sends the PDF.
- **Cost of the status quo:** ~15 offers/week across the team × ~2 h each ≈ 30 h/week, ~1,380 h/year (46 weeks); offers leave ~4 working days after the inquiry. [estimated]
- **Stakeholders & needs:**
  - Sales engineer (writes 2–3 offers a week) → a correct first draft in minutes instead of copy-paste
  - Head of Sales → faster offers, consistent quality
  - Inside sales assistant → fewer format corrections
  - IT → no extra system beside the CRM
- **Data situation:** CRM records (customer, contacts, installed base); ERP price list; ~3,000 old Word offers, inconsistently named. Whether a CRM export carries every offer field: nobody has checked. [unknown]
- **Earlier attempts:** A Word template with merge fields, dropped after a few months three years ago — configurations vary too much. [estimated]
- **Personal data:** yes (customer contact data from the CRM)
- **Legal / ethics / standards:** none known; offers are binding once sent
- **Strategy link:** Company goal 2026 "answer every qualified inquiry with an offer within 48 hours". [evidenced]
- **Riskiest assumption:** The CRM export contains every field an offer needs.
- **Minimum success criterion:** 8 of 10 standard offers finished from the draft in ≤ 30 minutes.
- **Views:** not relevant for this idea
- **Origin:** own idea

#### Evaluation

| Field | Light | Evidence | Origin | Committee note |
| --- | --- | --- | --- | --- |
| V1 Value mechanism & lead KPI | yellow | [estimated] | confirmed | Hours per offer 2 → ≤ 0.5; not measured yet |
| V2 Value volume | green | [estimated] | confirmed | 690 offers × 1.5 h ≈ 1,035 h ≈ 72k €/year; one dissent (yellow) |
| V3 Data situation & preparation effort · K.o. | yellow (estimate) | [estimated] | corrected | Card said unknown; IT lead estimates yellow, medium preparation |
| V4 Solution pattern & maturity | green | [estimated] | confirmed | Draft generation; standard feature, references known |
| V5 System character & learning loop | green | [estimated] | confirmed | Type A; sales operations maintains template and text blocks |
| V6 Effort class & operation · K.o. | green | [estimated] | confirmed | ~30k € build; operation 10 % sales operations + 2 h/month IT |
| V7 Damage class / verifiability | yellow / green | [estimated] | confirmed | Binding offer goes outward; engineer checks every draft |
| V8 Legal screening · K.o. | yellow | [estimated] | confirmed | Hosting of an external model open; contact: Data protection coordinator |
| V9 Ownership, strategy & adoption · K.o. | green | [evidenced] | confirmed | Head of Sales owns it; five of six engineers in favour |
| V10 Alternative & next test | green | [estimated] | confirmed | Mail merge covers ~30 min only; test: export five real records |

**K.o. gates** — one line each. A gate is never left open: the committee decides it, gives an estimate, or waives it.

- **V3 data:** estimate: yellow [estimated] (IT lead)
- **V6 effort:** pass (green, [estimated])
- **V8 legal:** pass (yellow, [estimated])
- **V9 ownership:** pass (green, [evidenced])

- **W (value):** (3 + 5 + 5) / 3 = 4.3 · **M (feasibility):** (3 + 5 + 5 + 5 + 5) / 5 = 4.6 · **R:** 0.6 (V7-damage and V8 yellow) · **Index:** **12**
- **Tendency:** conditional · **Confidence:** medium — nine fields [estimated], one [evidenced], no core field unknown after the V3 estimate
- **Drivers pro:** volume far above the build; committed owner and willing users; known pattern · **Drivers contra:** risk damper 0.6; data completeness only estimated; KPI not measured · **What would tip it:** the CRM export — below about two thirds of the offer fields, the saving falls under 1 h per offer.

**Committee rationale:** "The biggest block of hours in Sales, with the owner at the table. The open question is cheap to answer — answer it before building."

**Dissent:** One member rates V2 yellow — saved hours only count if they turn into more offers or faster follow-up.

#### Handover to maquette

- **Sponsor:** Head of Sales
- **Decision date:** 2026-10-15
- **Recommended mode:** workshop — conditional tendency with a defined cheap test; the demand is clear, discovery is not needed.
- **Prefill for sparring:**
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
- **Open before or during the maquette:**
  - Data situation [unknown] on the card, estimated yellow by the IT lead — run the five-record export before the workshop (V3)
  - Hosting and contract for an external model; works council information (V8, contact: Data protection coordinator)
  - Baseline for hours per offer and inquiry-to-offer days (V1)
  - New task split with inside sales (V9)
  - Dissent on V2: what the team does with the saved hours

### 2. EXG-002 — Service ticket triage

#### Card

- **Status:** evaluation-ready
- **Opportunity:** Service requests in the shared sales inbox are classified and forwarded to the right service group automatically.
- **Department(s):** Sales, Service
- **Process & systems:** Customers write to the sales address; inside sales forwards service cases by hand to one of three groups (repair, spare parts, commissioning), which log them in the ticket system.
- **Cost of the status quo:** ~40 service e-mails per working day × ~3 min sorting ≈ 2 h per day, ~440 h per year; misrouted requests lose about a day. [estimated]
- **Stakeholders & needs:**
  - Inside sales assistant (sorts the inbox each morning) → service mail sorted without reading each one
  - Service groups → complete requests first time
  - Customer → same-day reply from the right person
- **Data situation:** ~18 months of inbox archive; forwards show the group, no systematic labels. [estimated]
- **Earlier attempts:** Keyword mail rules, switched off after misrouting sales inquiries. [estimated]
- **Personal data:** yes (customer contact data in e-mails)
- **Legal / ethics / standards:** none known
- **Strategy link:** Service goal "first response within one working day" (document not seen). [estimated]
- **Riskiest assumption:** The right service group can be read from the e-mail text alone.
- **Minimum success criterion:** 9 of 10 service e-mails reach the right group without a human touch.
- **Views:** View A: most e-mails are obvious. / View B: the few unclear ones cause most of the delay.
- **Origin:** conversation

#### Evaluation

| Field | Light | Evidence | Origin | Committee note |
| --- | --- | --- | --- | --- |
| V1 Value mechanism & lead KPI | yellow | [estimated] | confirmed | KPI hours to first response, not measured |
| V2 Value volume | yellow | [estimated] | confirmed | 440 h × 70 € ≈ 31k €/year, comparable to the build |
| V3 Data situation & preparation effort · K.o. | yellow | [estimated] | confirmed | Archive exists, labels to derive |
| V4 Solution pattern & maturity | green | [estimated] | confirmed | Classify-and-route, standard |
| V5 System character & learning loop | yellow | [estimated] | corrected | Type B, upkeep open (moderator: green) |
| V6 Effort class & operation · K.o. | yellow | [estimated] | confirmed | 10–50k; "IT will handle it" |
| V7 Damage class / verifiability | yellow / yellow | [estimated] | confirmed | Customer waits; misroutes surface late |
| V8 Legal screening · K.o. | green | [estimated] | confirmed | Usual contact data only |
| V9 Ownership, strategy & adoption · K.o. | yellow | [estimated] | confirmed | Head of Service not yet asked |
| V10 Alternative & next test | yellow | [estimated] | confirmed | Separate service address unchecked |

**K.o. gates** — one line each. A gate is never left open: the committee decides it, gives an estimate, or waives it.

- **V3 data:** pass (yellow, [estimated])
- **V6 effort:** pass (yellow, [estimated])
- **V8 legal:** pass (green, [estimated])
- **V9 ownership:** pass (yellow, [estimated])

- **W (value):** (3 + 3 + 3) / 3 = 3.0 · **M (feasibility):** (3 + 5 + 3 + 3 + 3) / 5 = 3.4 · **R:** 0.8 (V7-damage yellow, V8 green) · **Index:** **8**
- **Tendency:** conditional · **Confidence:** medium — all fields [estimated], no core field unknown
- **Drivers pro:** standard pattern; daily pain · **Drivers contra:** volume only comparable to the build; owner not involved · **What would tip it:** whether a separate service e-mail address already removes most of the sorting.

**Committee rationale:** "Worth doing, not now: Service is in the ERP migration until end of Q1 2027 and its head has not been asked. Check the simple alternative first."

**Dissent:** none

#### Handover to maquette

- **Sponsor:** Head of Service (to be confirmed)
- **Decision date:** open
- **Recommended mode:** discovery — owner and demand still to confirm; not before the revisit date.
- **Prefill for sparring:**
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
- **Open before or during the maquette:**
  - Head of Service as owner and sponsor (V9)
  - Separate service e-mail address as non-AI alternative (V10)
  - Operator with a time share (V6)
  - Service goal document not seen (Strategy link)
  - Views A/B: share of unclear e-mails — count one week of mail

## Parked / rejected

| ID | Title | Decision | Reason | Revisit when |
| --- | --- | --- | --- | --- |
| EXG-002 | Service ticket triage | parked | rank 2, no maquette now: Service bound by ERP migration, owner not involved | after ERP go-live, end of Q1 2027, with the Head of Service |

## Notes (human)

