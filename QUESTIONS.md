# idea — Every question the skillset asks a human

**Version 4 (idea 0.3.2).** One row per question, in the order it is asked. **The IDs are stable identifiers** — `profile/questions.md` (setup skill) refers to them; renumbering is a breaking change. The rule behind the list: a question is asked once, prefilled where an earlier file already answers it, and never re-asked by a later stage. "Prefilled from" names that source; "—" means the question is genuinely this stage's own. Wording is the skill's canonical form; the conversation adapts it to the user's language.

## Director (`idea`) — first call only

| # | Question | Prefilled from | Note |
| --- | --- | --- | --- |
| D1 | Which company or department — and a 2–5 letter code that prefixes every card ID? (proposed, user corrects) | profile | once per workspace |
| D5 | Track: are we looking for ideas (explore) — or is the project fixed and we collect what every stakeholder needs from it (focus)? | profile (`Track:` line) | once per workspace, never changed; asked right after D1 |
| D2 | Mode of collect: solo, collector, or import? | — | explore only; may change per session |
| D3 | Git: is the folder a repository? | checked silently, result told | never `git init`; a clone of the public repo counts as no |
| D4 | Language of the result files? | profile → chat language → explicit statement | confirmed in half a sentence |

On later calls the Director asks at most one question: which of two possible next steps (collect again / evaluate; evaluate more / close with shortlist). A merge is started by the user's word or the committee's request, not by a Director question; the Director may mention visible overlaps in half a sentence.

## Card operations — idea-merge (consolidator)

Optional; runs between collect and evaluate or inside an evaluate round. One group of cards at a time.

| # | Question | When | Prefilled from | Field |
| --- | --- | --- | --- | --- |
| M1 | Consolidate, umbrella or split? | per group | the user's wording; proposed from the cards | operation |
| M2 | Which cards belong together — or, for a split, which card? (candidate groups proposed: cards · why · operation) | opening | card index, card contents | Relation, `input` |
| M3 | Title and opportunity of the new card (per part for a split)? | per operation | source cards (proposed) | title, Opportunity |
| M4 | These values differ between the sources — take one, or keep both as views? | per conflicting field | source cards | the field, Views |
| M5 | Which riskiest assumption and which minimum success criterion hold for the new card (per part for a split)? | per operation | sources' pre-mortem lines (proposed) | Riskiest assumption, Minimum success criterion |
| M6 | Umbrella: what distinguishes each variant? · Split: what are the parts, and which content goes to which part? (allocation read back as one table) | umbrella / split | source card(s) | Variants / allocation |

Personal data takes the strictest value of the sources without asking; legal constraints and stakeholder needs are unions with `← <ID>` — shown in the read-back, not asked.

## Stage 1 — idea-collect (interviewer)

Collect is an interview, not a questionnaire: the fixed questions below frame it, the probe catalogue and toolkit (§1–§3 of the skill) supply the follow-ups, one at a time.

| # | Question | When | Prefilled from | Card field |
| --- | --- | --- | --- | --- |
| C1 | What does the department do — main processes in a sentence or two; company goals or an AI/data strategy if known? | opening | `00-idea.md`, profile | Department(s), Strategy link |
| C2 | Walk me through yesterday, from arriving to leaving. | cold start only | — | (entry point for probes) |
| C3 | Probe of choice: annoying tasks · tasks nobody wants · high error rates · delayed processes · spreadsheets that no longer work · e-mail floods · version chaos · data silos · coordination problems · missing knowledge | core loop, per thread | — | Opportunity, Process & systems |
| C4 | Tell me about the last time this happened — how often, how long, who all? (make it concrete) | per thread | — | Cost of the status quo `[evidence]` |
| C5 | Did I get this right: …? (replay, deliberately slightly wrong when useful) | per thread | — | Process & systems |
| C6 | Was this tried before — why did it fail? | per thread | — | Earlier attempts `[evidence]` |
| C7 | Personal data involved? Legal, ethics, works council, norms? | per card | — | Personal data, Legal / ethics / standards |
| C14 | Who would use it — internal team, company-wide, or external / public — and roughly how many? When are the peaks, is office hours enough or 24×7, and which systems or providers would it depend on? | per card | — | Users & scale |
| C8 | Which departments do you work with most — and per handoff: what arrives late, wrong, twice or not at all? | interface round, before a regular close | — | interface cards, both departments |
| C9 | Before I suggest anything — which ideas do you already have in mind? (quantity target ~8) | ideas step, silent-first | — | new cards, Origin: own idea |
| C10 | Which of these AI patterns fits the pains we modelled — knowledge assistant · read-and-check · draft generation · report automation · classify-and-route · forecast · translate? (several, never one) | after C9, model rich | — | new cards, Origin: AI pattern suggestion |
| C11 | Imagine the solution has been in use for a year and counts as a failure. Which of the success criteria is the most likely to have been missed — and why? | mini pre-mortem, per card | — | Riskiest assumption (inverted) |
| C12 | What would it at least have to achieve for you to really use it? (measurable if possible) | mini pre-mortem, per card | — | Minimum success criterion |
| C13 | Shall we freeze what we have and do the rest in a second session? | near budget | — | — |
| I1 | Import: here are the columns I found and the mapping I propose — corrections? | import mode, unknown format only | `00-idea.md` "Imports" for known formats | (mapping) |
| I2 | Import: the interview questions above, but **only for fields the format left `[unknown]`**, starting with C4 and C11/C12 | import mode | the imported card | gaps only |

Collector mode adds a briefing (question guide from C3–C7 for the colleague conversation) and a debriefing (C4–C7 as follow-ups on the report); no new question types.

Every question in every stage may be skipped (RULES §5): it is not re-asked, the field becomes `[unknown]`. Gate and safety questions wait for an answer.

## Stage 2 — idea-evaluate (committee moderator)

| # | Question | When | Prefilled from | Field |
| --- | --- | --- | --- | --- |
| E1 | Who is at the table (roles), and who writes? | opening | — | Session |
| E2 | Which cards in this round, in which order? | opening | card index (read back) | Session |
| E3 | Effort classes for V6 — defaults < 10k / 10–50k / > 50k? | opening | profile | Session |
| V1 | Where exactly does the value come from — time, errors, speed, revenue, risk — and how would you measure it? | per card | Opportunity, Minimum success criterion | V1 |
| V2 | How often, how much each time, how many people — roughly per year? | per card; revisited after V6 | Cost of the status quo | V2 |
| V3 | Which data does the solution need — does it exist, digital, accessible, current? preparation little / medium / much, whose time? | per card, K.o. | Data situation | V3 |
| V4 | What kind of AI solution — knowledge assistant, read-and-check, draft generation, classify-and-route, forecast, translate, other? products on the market, references? | per card | "Imported" section | V4 |
| V5 | A fixed process where AI does one step (A), a curated system needing upkeep (B), or a system that learns from operation (C)? who maintains it? could it be one class simpler? | per card | — | V5 |
| V6 | Which effort class for the build — and which operating model is plausible: internal, a service provider, or unclear? Does running cost grow with use — roughly what per use, against the value per use? (names, time shares and cost figures are asked in build intake) | per card, K.o. | "Imported" section | V6 |
| V7 | If the AI is wrong once and nobody notices — worst case? And can one tell right from wrong, how fast? | per card, two lights | — | V7 damage / verifiability |
| V8 | Personal data? certifications or norms touched? works council? may data leave the house? — who is the contact for anything yellow? | per card, K.o. | Personal data, Legal / ethics / standards | V8 |
| V9 | Who owns the process and stands behind the idea? do future users want it? which company goal? who loses something? | per card, K.o. | Strategy link, Stakeholders & needs | V9 |
| V10 | If AI were no option — how else? what must be true for the idea to hold, and what is the cheapest way to find out? | per card | Riskiest assumption, Earlier attempts | V10 |
| G1 | Green, yellow or red — and in one sentence, why? | after every field | (the light is proposed first) | origin: confirmed / corrected |
| G2 | This gate is unknown: can you estimate it — or is it not relevant for this idea? | per unknown K.o. gate | — | estimate `[estimated]` (who) / waiver (reason) |
| G3 | This point blocks everything further — what would have to happen for it to stop blocking? | per confirmed red gate | — | resolution condition, status parked |
| S1 | Here are all evaluations — in which order do we rank them, and if it deviates from the index, why? | closing | evaluations (read back) | Ranking, rationale |
| S2 | Per shortlisted entry: who is the sponsor who decides after the maquette? | closing | — | Handover: Sponsor |
| S3 | Decision date? | closing | — | Handover: Decision date |
| S4 | Workshop or discovery? (proposed from V6 and tendency) | closing | V6, tendency | Handover: Recommended mode |
| S5 | Any dissent to record? | closing, per entry | — | Dissent |
| S6 | For every card not shortlisted: reason and revisit condition? | closing | consumed cards: `merged into` / `split into` (not asked) | Parked / rejected |
| S7 | Which entry goes into the next maquette — and for an umbrella, which variant(s) does the demo show? | closing, once | ranking | Maquette order, `next_maquette` |

## Focus track

Runs instead of the stages above when `00-idea.md` says `track: focus`. The project is fixed; stakeholders contribute, a consolidator joins, a committee decides. Explore IDs are never used in focus and the reverse.

### Stage 1 — idea-focus-collect (interviewer): the frame, first session only

| # | Question | Prefilled from | Frame section |
| --- | --- | --- | --- |
| FF1 | What goes wrong today, for whom, how often? | profile `scope.md`, material | Problem |
| FF2 | What must the project achieve — and what must it at least achieve to be used? | profile | Goal and minimum success |
| FF3 | What is in, what is deliberately out? | profile `scope.md` | Scope |
| FF4 | Here are the known facts — anything wrong or missing? | profile `scope.md` "Known context" (only confirmed) | Known context |
| FF5 | Is the kind of solution already fixed? | profile | Solution pattern |
| FF6 | Whose view do we need — roles, each with a 2–4 letter code? | profile `scope.md` departments | Perspectives |
| FF7 | Does the product run differently at different places, channels or for different user groups? (optional) | — | Touchpoints / variants |
| FF8 | Who will use it — internal team, company-wide, or external / public — and roughly how many? Peaks, office hours or 24×7, critical systems or providers? | profile `scope.md` | Users and scale |

### Stage 1 — idea-focus-collect (interviewer): a contribution session

| # | Question | When | Contribution type |
| --- | --- | --- | --- |
| FC1 | Which perspective do you speak for — your role in relation to the project? | opening | (session header) |
| FC2 | Walk me through the situation today, the last time it happened — what takes time, what goes wrong, what is annoying? | per session | concern, goal |
| FC3 | What must the product achieve for you — how would you notice it works? | per session | goal (Measure) |
| FC4 | What conditions must it respect — workflow, roles and responsibility, time pressure, training, law and data protection, IT and operation, cost? | per session | constraint |
| FC5 | What must it do — and what would be nice to have? | per session | requirement, wish |
| FC6 | What must it never do? | per session | constraint |
| FC7 | Imagine the product has been in use for a year and counts as a failure. What went wrong? | per session | concern |
| FC8 | What must it at least achieve for you to really use it? | per session | goal (Measure) |
| FC9 | Anything else — also ideas outside this project? | per session | out-of-scope, question |
| FC10 | Here are all your contributions — did I get you right? Which are must, should, could for you? | closing, read-back gate | Priority (contributor) |
| FI1 | Import: here is the mapping I propose for this returned file — corrections? | import, unknown format only | (mapping) |
| FI2 | Import: priority and measure, only where the return left them open | import, if the person is available | gaps only |

Collector mode: a question guide from FC2–FC9 before, the debrief after; no new question types. Without file access (prompt file): the same questions, the session printed as one markdown block at the end.

### Stage 2 — idea-focus-consolidate (consolidator)

| # | Question | When | Result |
| --- | --- | --- | --- |
| FN1 | These words seem to mean the same thing — which term do we use? | once, before the first type | Glossary |
| FN2 | These contributions say the same thing — right? (proposed items per type) | per type | Items, Sources |
| FN3 | These contradict each other — is it a contradiction, or two different things? | per type | Conflicts (never resolved here) |
| FN4 | These items could stop the whole project — flag them for the committee? | once | K.o. candidates |

Priorities are not asked here; the contributors' own values are carried.

### Stage 3 — idea-focus-review (committee moderator)

| # | Question | When | Prefilled from | Result |
| --- | --- | --- | --- | --- |
| FR1 | Who is at the table (roles), and who writes? Is everyone who should decide present? | opening | — | Session (`Complete:` yes or partial) |
| FR2 | Here are all ten lights for the project, each with the items it rests on — corrections? | once, one table | register draft, frame | Project check |
| FR3 | Does this stop the project — pass, pass with a condition, or fail? (fail: what would have to happen for it to stop blocking?) | per K.o. candidate and per non-green K.o. field | draft K.o. candidates | K.o. decisions; a condition becomes a MUST item |
| FR4 | Outcome go / go with conditions / stop — and what would tip it? | once | K.o. decisions | Outcome |
| FR5 | View A, view B, both as variants, or an open question? | per conflict | draft conflicts | Decided conflicts |
| FR6 | Here are the proposed priorities — corrections? (won't → out of scope, with reason) | per type, one table | contributors' priorities | Register priority |
| FR7 | Next stage: maquette or build? | closing | installation | Handover, `next` |
| FR8 | Which items must the maquette show? | closing, maquette only | MUST items | Demo focus |
| FR9 | Who is the sponsor who decides after the next stage? | closing | — | Handover |
| FR10 | Decision date? | closing | — | Handover |
| FR11 | (second round, partial committee) Here is the register as the first round decided it — where do you disagree (light, K.o. decision, conflict, priority, demo focus, sponsor)? Anything new that must be in? | second round only | previous `10-register.md` | Session *Changes since*, Register |

## What idea hands over and never asks again

`10-shortlist.md` (contract H1/2) carries the Maquette order (which entry maquette builds next, which variant the demo shows) and, per entry, every card field verbatim incl. Relation and the Variants table, plus V1–V10 with lights and notes, the K.o. lines, sponsor, decision date, mode, rationale, dissent, and the prefill mapping for maquette's sparring. maquette proposes the Maquette order entry (D1 becomes a confirmation) and confirms the entry's content in one block; the only sparring questions that remain are its own (Q1 evidence, Q3 situation and consequence, Q4 demo decision) — see `maquette/QUESTIONS.md`.

In focus, `10-register.md` (contract `register/1`) carries the frame, the project check with K.o. decisions and outcome, every item `R-<n>` with priority, sources and measure, the decided conflicts, the glossary, the open questions and the handover. The next stage confirms the frame and the demo focus instead of asking again, and turns the open questions into its own `OQ-n`.
