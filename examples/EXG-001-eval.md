---
stage: evaluation
owner: idea-evaluate
status: done
revision: 3
created: 2026-09-15T10:05
updated: 2026-09-15T10:48
input: cards/EXG-001-card.md@4
---
<!-- Example — fictitious Example GmbH. Shows what a finished file looks like; not a template. -->

# Evaluation EXG-001: Offer draft assistant

_Ten-field evaluation of one idea card, Kriterienkatalog Konzeptbewertung v0.3. Every light is proposed by the moderator and confirmed or corrected by the committee; every field carries an evidence mark. The index is derived, never the statement itself._

- **Committee:** Managing Director, Head of Sales, IT lead, Data protection coordinator · **Writer:** Sales operations coordinator
- **Date:** 2026-09-15
- **Effort classes:** `< 10k` / `10–50k` / `> 50k` (defaults, no profile)
- **Card status at evaluation:** done
- **Result status:** complete

## V1 — Value mechanism & lead KPI

**Light:** yellow · **Evidence:** [estimated] · **Origin:** confirmed
Lever: time. Lead KPI: hours per standard offer, ~2 → ≤ 0.5; not measured. Secondary: inquiry-to-offer days, ~4 → ≤ 2 (dates are in the CRM, not reported).
_Reason:_ Lever clear and target set, but the current value is estimated and the measurement must be built.

## V2 — Value volume

**Light:** green · **Evidence:** [estimated] · **Origin:** confirmed
15 offers/week × 46 weeks = 690 offers/year. Saving 1.5 h each → ~1,035 h/year × 70 €/h internal rate ≈ 72k €/year, against a build in class 10–50k.
_Reason:_ Even at half the saving (~36k €/year) the volume clearly exceeds the effort class.

## V3 — Data situation & preparation effort · K.o.

**Light:** estimate: yellow [estimated] (IT lead) · **Evidence:** [estimated] · **Origin:** estimated (moderator)
CRM has an export interface and is maintained. ~200 recent, clean offers must be selected as text-block source (medium preparation, ~3 days of a sales engineer). Field completeness of the export unchecked.
_Reason:_ The committee asked the IT lead to estimate the unknown: data exists and is reachable, preparation medium.

## V4 — Solution pattern & maturity

**Light:** green · **Evidence:** [estimated] · **Origin:** confirmed
Pattern: draft generation from structured data plus text blocks. A standard feature of several CRM and office-suite vendors; the IT lead knows two comparable manufacturers using it.
_Reason:_ Known pattern, standard products, references in comparable houses.

## V5 — System character & learning loop

**Light:** green · **Evidence:** [estimated] · **Origin:** confirmed
Type A: fixed template, the AI step fills the scope text. The sales operations coordinator maintains template and text-block library, which stays in the house.
_Reason:_ Type A with a named maintenance role; a learning system is not needed for the purpose.

## V6 — Effort class & operation · K.o.

**Light:** green · **Evidence:** [estimated] · **Origin:** confirmed
Build ~30k € (class 10–50k). Operation: sales operations coordinator ~10 % for content; IT ~2 h/month for the interface.
_Reason:_ Class plausible and within frame; operators named with time shares.

## V7 — Damage class & verifiability · two lights

**Light damage:** yellow · **Light verifiability:** green · **Evidence:** [estimated] · **Origin:** confirmed
Worst case: a wrong price or pump specification in a binding offer. The sales engineer reviews every draft; each value traces back to a CRM or ERP field.
_Reason:_ Effect outward, but objective right/wrong exists and the check is part of the process.

## V8 — Legal screening · K.o.

**Light:** yellow · **Evidence:** [estimated] · **Origin:** confirmed
Usual customer contact data. Open: may CRM data go to an externally hosted model, under which contract? No certification touched; works council to be informed (no individual performance measurement). **Contact person:** Data protection coordinator.
_Reason:_ Personal data and hosting question present, resolvable, contact named.

## V9 — Ownership, strategy & adoption · K.o.

**Light:** green · **Evidence:** [evidenced] · **Origin:** confirmed
Owner and sponsor: Head of Sales. Team meeting minutes 2026-09-03: five of six sales engineers want to try it. Goal: 48-hour offers. Who loses: inside sales loses part of the format checks (moves to follow-up calls).
_Reason:_ Owner named and committed, users asked and in favour, goal documented.

## V10 — Alternative & next test

**Light:** green · **Evidence:** [estimated] · **Origin:** confirmed
Non-AI alternative: mail merge — covers header and price fields (~30 min of 2 h), not the scope text; tried before. Riskiest assumption: the CRM export contains every offer field. Cheapest test: export five real records from last month and mark missing fields — half a day, IT lead plus one sales engineer.
_Reason:_ Alternative checked and inferior; assumption named; test cheap and concrete.

## Assessment

- **K.o. gates:** V3 estimate (yellow, IT lead) · V6 pass · V8 pass · V9 pass
- **W (value):** (3 + 5 + 5) / 3 = 4.3
- **M (feasibility):** (3 + 5 + 5 + 5 + 5) / 5 = 4.6
- **R (risk damper):** 0.6 — V7-damage and V8 both yellow
- **Index:** round(4.3 × 4.6 × 0.6) = round(11.9) = **12**
- **Confidence:** medium — one field [evidenced], nine [estimated]; none of V1, V2, V3, V6 is [unknown] after the V3 estimate

## Recommendation

- **Tendency:** conditional
- **Drivers pro:** Volume far above the build; committed owner, willing users; known pattern.
- **Drivers contra:** Risk damper 0.6 (binding offers; hosting open); data completeness only estimated; KPI not measured.
- **What would tip the assessment:** The CRM export: below about two thirds of the offer fields, the saving drops under 1 h per offer and V3 moves towards red.
- **Next step:** maquette (workshop) — run the five-record export first and bring its result to the workshop.

## Dissent

One member rates V2 yellow: saved hours only become value if they turn into more offers or faster follow-up, which the team has not yet planned.

## Open / to clarify

- V3: the IT lead's estimate replaces the card's [unknown] — confirm with the five-record export (IT lead, one sales engineer).
- V1: baseline — hours per offer (anonymous team self-report, four weeks) and inquiry-to-offer days from the CRM.
- V8: hosting and contract for an external model; works council information (contact: Data protection coordinator).
- V9: agree the new task split with inside sales.

## Notes (human)

