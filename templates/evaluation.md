---
stage: evaluation
owner: idea-evaluate
status: in_progress          # open | in_progress | done | skipped | superseded (source card consumed by idea-merge — set by the Director)
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: cards/<ID>-card.md@<rev>        # for a merge card also the superseded evaluations used for prefill: evaluations/<ID>-eval.md@<rev>
---

# Evaluation <ID>: <card title>

_Ten-field evaluation of one idea card, Kriterienkatalog Konzeptbewertung v0.3. Every light is proposed by the moderator and confirmed or corrected by the committee; every field carries an evidence mark. The index is derived, never the statement itself._

- **Committee:** <roles, anonymised> · **Writer:** <role>
- **Date:** <YYYY-MM-DD>
- **Effort classes:** <`< 10k` / `10–50k` / `> 50k`, or the profile's thresholds>
- **Card status at evaluation:** <sketch | done>
- **Result status:** <in_progress | complete | parked>

<!-- Per field: light green|yellow|red (or waiver / unknown), evidence [evidenced|estimated|unknown], origin proposed|confirmed|corrected|estimated (moderator) — the last one for a K.o. field that was [unknown] and was settled by the committee's estimate, one sentence of reasoning, dissent if any. Anchors are given per field for the writer. -->

## V1 — Value mechanism & lead KPI

**Light:** <green|yellow|red> · **Evidence:** [evidenced|estimated|unknown] · **Origin:** <proposed|confirmed|corrected|estimated (moderator)>
<the one main lever; lead KPI: current → target; is it measured today?>
_Reason:_ <one sentence>
<!-- green: lever clear, KPI measured today, current and target known · yellow: lever clear, KPI plausible but current value estimated or measurement must be built · red: no measurable KPI — value stays "better/faster" without a reference -->

## V2 — Value volume

**Light:** <…> · **Evidence:** <…> · **Origin:** <…>
<frequency × saving × people, extrapolated per year — show the arithmetic>
_Reason:_ <one sentence>
<!-- green: extrapolation solid, clearly above the effort class · yellow: comparable to the effort, or strongly varying · red: effect spotty or visibly below the effort -->

## V3 — Data situation & preparation effort · K.o.

**Light:** <green|yellow|red | estimate: … [estimated] (who) | waiver: … (committee, date) | unknown> · **Evidence:** <…> · **Origin:** <…>
<which data, where, current, complete, accessible; preparation little/medium/much; whose time>
_Reason:_ <one sentence>
<!-- green: data exists, digital, accessible, current, little preparation · yellow: exists but scattered, inconsistent or access to clarify; medium preparation · red: data does not exist, not digital, or access foreseeably unobtainable → K.o. -->

## V4 — Solution pattern & maturity

**Light:** <…> · **Evidence:** <…> · **Origin:** <…>
<pattern: knowledge assistant | read-and-check | draft generation | classify-and-route | forecast | translate | other; products on the market; references>
_Reason:_ <one sentence>
<!-- green: known pattern, standard products, references in comparable houses · yellow: pattern known, but bespoke fit and integration; few references · red: no fitting pattern — state of research, not state of the art -->

## V5 — System character & learning loop

**Light:** <…> · **Evidence:** <…> · **Origin:** <…>
<type A software with an AI step | B curated AI system | C learning system; who maintains or monitors; could it be one class simpler; does a knowledge asset arise and does it stay in the house?>
_Reason:_ <one sentence>
<!-- green: type A, or a justified B/C with a named maintenance role · yellow: B/C without settled upkeep, or type unclear · red: type C intended but no feedback, validation or upkeep imaginable; or the type far exceeds the purpose. System type is not autonomy degree — do not conflate. -->

## V6 — Effort class & operation · K.o.

**Light:** <green|yellow|red | estimate: … | waiver: … | unknown> · **Evidence:** <…> · **Origin:** <…>
<effort class for the build; who operates it permanently — name and time share>
_Reason:_ <one sentence>
<!-- green: class plausible and within frame; operator named with a time share · yellow: class uncertain, or operation only informal ("IT will handle it" is yellow at best) · red: nobody operates it permanently → K.o. -->

## V7 — Damage class & verifiability · two lights

**Light damage:** <green|yellow|red> · **Light verifiability:** <green|yellow|red> · **Evidence:** <…> · **Origin:** <…>
<worst case if one wrong result goes unnoticed; can right/wrong be told, how fast is an error noticed>
_Reason:_ <one sentence>
<!-- damage — green: internally correctable, few consequences · yellow: effect outward (customer, supplier, authority) · red: harm to persons, safety, assets or reputation. verifiability — green: objective right/wrong exists, errors visible · yellow: partly subjective, or errors surface late · red: no practicable check -->

## V8 — Legal screening · K.o.

**Light:** <green|yellow|red | estimate: … | waiver: … | unknown> · **Evidence:** <…> · **Origin:** <…>
<personal data of employees or customers; certifications or norms touched; works council; may data leave the house; **contact person** for anything yellow>
_Reason:_ <one sentence>
<!-- green: no personal data beyond the usual, no relevant regulation touched, co-determination uncritical · yellow: personal or norm reference present, resolvable — with a named contact · red: visible blocker: inadmissible processing, breach of a certification, unacceptable data outflow, clear rejection by co-determination → K.o. The moderator never assesses legality. -->

## V9 — Ownership, strategy & adoption · K.o.

**Light:** <green|yellow|red | estimate: … | waiver: … | unknown> · **Evidence:** <…> · **Origin:** <…>
<process owner and whether they stand behind it; do future users want it; which company goal; who loses something (one line)>
_Reason:_ <one sentence>
<!-- green: process owner named and behind it; users want it; clear link to a company goal · yellow: sponsor unclear, users not asked or sceptical, or strategy link constructed · red: no process owner — or future users reject it → K.o. -->

## V10 — Alternative & next test

**Light:** <…> · **Evidence:** <…> · **Origin:** <…>
<non-AI alternative considered and why inferior; the riskiest assumption; the cheapest test>
_Reason:_ <one sentence>
<!-- green: non-AI alternative checked and inferior; riskiest assumption named, cheap test available · yellow: alternative not cleanly checked, or the test is expensive/unclear · red: a simpler non-AI solution achieves the same -->

## Assessment

- **K.o. gates:** V3 <pass|fail|estimate|waiver|unknown> · V6 <…> · V8 <…> · V9 <…>
- **W (value):** (<V1> + <V2> + <V9>) / <n> = <…>
- **M (feasibility):** (<V3> + <V4> + <V5> + <V6> + <V7-verifiability>) / <n> = <…>
- **R (risk damper):** <1.0 | 0.8 | 0.6> — <reason>
- **Index:** round(<W> × <M> × <R>) = **<1–25>** <or "no score — parked" | "provisional — low confidence">
- **Confidence:** <high | medium | low> — <reason from the evidence marks>

## Recommendation

- **Tendency:** <rather go | conditional | rather no-go | parked | not yet assessable>
- **Drivers pro:** <the two or three strongest points>
- **Drivers contra:** <the two or three weakest points>
- **What would tip the assessment:** <the one assumption>
- **Next step:** <maquette (workshop | discovery) | test the riskiest assumption: … | resolution condition: … | clarify first: …>

## Dissent

<anonymised, one sentence per dissenting view, or "none">

## Open / to clarify

- <open fields, unanswered questions, named contact persons, waivers with their reasons>

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
