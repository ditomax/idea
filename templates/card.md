---
stage: card
owner: idea-collect
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: —                     # or import:<file> when the card was mapped from a foreign format
source: interview            # interview | import:<format, e.g. xlsx-12col> | mixed
---

# Idea card <ID>: <short, telling name>

_Result of idea-collect. One card per idea, written in the language set for result files. Field set inherited from ki-ideenfindung v0.8. A card is **evaluation-ready** when no field is empty — `[unknown]` is a valid value, an empty field is not. Evidence marks: `[evidenced]` (in a document), `[estimated]` (from conversation), `[unknown]` (nobody knows yet)._

- **Status:** <sketch | evaluation-ready>
- **Opportunity:** <the improvement potential in 1–2 sentences, phrased as an opportunity>
- **Department(s):** <own department; both for an interface idea>
- **Process & systems:** <the affected workflow as it runs today, the systems and artefacts involved>
- **Cost of the status quo:** <frequency × effort, otherwise quality/frustration> [evidenced|estimated|unknown]
- **Stakeholders & needs:** <role → need, one per line>
- **Data situation:** <sources, format, quality> [evidenced|estimated|unknown]
- **Earlier attempts:** <what was tried and why it failed, or "none known"> [evidenced|estimated|unknown]
- **Personal data:** <yes | no | unclear>
- **Legal / ethics / standards:** <constraints, or "none known">
- **Strategy link:** <which company goal the idea supports> [evidenced|estimated|unknown]
- **Riskiest assumption:** <from the mini pre-mortem: the success criterion most likely to be missed, inverted>
- **Minimum success criterion:** <what the solution must at least achieve to be used; measurable if possible>
- **Views:** <only on contradictions: "View A: … / View B: …", anonymised; otherwise omit>
- **Origin:** <own idea | conversation | AI pattern suggestion | import>

## Imported, no field in this card

<!-- Only when source is import. Content of foreign columns that have no counterpart above (e.g. "technical prerequisites", "cost estimate"). Kept verbatim so nothing disappears; idea-evaluate may use it for V4/V6. Otherwise: "—". -->

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
