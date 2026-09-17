# idea — Shared Rules for All Stage Skills

**Version 2** (idea 0.2.0: card operations, H1/2). Every stage skill reads this file before doing anything. The Director (`idea`) enforces it. If a stage skill and this file disagree, this file wins. The rules are the same core as maquette's `RULES.md` v2 — one suite, one discipline.

## 1. Vocabulary

- **Idea workspace** — one folder holding everything the idea skillset produces for one organisation or department: the control file, the cards, the evaluations, the shortlist.
- **Stage** — one of: collect → (merge) → evaluate. Collect produces cards, merge produces cards from cards, evaluate produces evaluations and the shortlist. Merge is optional and may also run in the middle of an evaluate round.
- **Card** — one idea, one file: `cards/<ID>-card.md`. Written by idea-collect, or by idea-merge for a card produced from other cards.
- **Card operation** — idea-merge's work: **consolidate** (n cards → 1, sources consumed), **umbrella** (n cards → 1 umbrella card, sources stay active as its **variants**), **split** (1 card → n, source consumed). A **consumed** card keeps its file and ID; its evaluation becomes `superseded`.
- **Evaluation** — the ten-field assessment of one card: `evaluations/<ID>-eval.md`. Written by idea-evaluate.
- **Shortlist** — `10-shortlist.md`, the ranked handover to maquette (contract H1). Written by idea-evaluate.
- **Director** — the `idea` skill. Reads the workspace, tells the user where they are, calls the stage skill, keeps `00-idea.md` true.
- **Profile** — an optional `profile/` folder with customer-specific constraints (see §8).
- **Human notes** — the section `## Notes (human)` at the end of every result file.

## 2. Folder is the state

There is no state outside the idea workspace — no `~/.something`, no environment variables, no memory across workspaces. A skill learns everything it needs by reading `00-idea.md`, its input files and (if present) the profile. A skill that needs something else asks the user.

Two layouts are supported; the Director resolves which one applies at start and calls the workspace `<work>`:

| Layout | `<suite>` (read-only) | `<work>` | profile |
| --- | --- | --- | --- |
| standalone workspace | the folder holding `AGENTS.md`, `VERSION` | `<suite>/ideas/<org-code>/` | `<suite>/profile/` |
| inside a project | `<project>/planning/suite/idea/` | `<project>/planning/idea/` | `<project>/planning/profile/` |

The project layout is recognised by a `planning/` folder above `<suite>`. In the project layout there is exactly one workspace; in the standalone layout there may be several (one per organisation or department).

```
<work>/
  00-idea.md                 Director        control: org, language, mode, sessions, card index, imports
  cards/<ID>-card.md         idea-collect    one idea per file
                             idea-merge      cards produced by consolidate, umbrella, split
  evaluations/<ID>-eval.md   idea-evaluate   ten fields, arithmetic, tendency, confidence
  10-shortlist.md            idea-evaluate   ranked handover to maquette (contract H1/2)
```

## 3. Frontmatter

Every result file starts with:

```yaml
---
stage: <control|card|evaluation|shortlist>
owner: <skill name>
status: <open|in_progress|done|skipped>
revision: <integer, starts at 1>
created: <ISO timestamp, minutes>
updated: <ISO timestamp, minutes>
input: <file>@<revision>[, <file>@<revision>]
---
```

Paths in `input` are relative to `<work>` (`cards/EXG-003-card.md@3`, `evaluations/EXG-007-eval.md@1`), never from the project root.

`00-idea.md` additionally carries `org`, `code`, `language`, `git`, `profile` and the session log. Stage skills read those; only the Director writes them. `card.md` adds `source`; `10-shortlist.md` adds `contract`. A template may add stage-specific fields — copied from `00-idea.md` or defined in the template, never invented.

## 4. Write rules

1. **One owner per file.** Write only files whose `owner` is your skill name. Read anything. If you believe another file is wrong, say so to the user and record it under "Open questions" in *your* file.
2. **Done is frozen.** Never modify a file whose `status` is `done`. A rerun ("redo") writes `<name>.v2.md` (then `.v3.md` …) with `revision: 1` in the new file. The Director records which version is current in `00-idea.md`. Exception: a card with status `sketch` is not done — collect may complete it in a later session (revision + 1).
3. **Findings flow forward, never backward.** What evaluate learns about a card goes into the evaluation, not into the card. Only the shortlist consolidates — and idea-merge, which writes *new* cards from existing ones and never touches the sources.
4. **Optimistic locking.** Before writing: read the file, note `revision`. When writing: set `revision + 1` and `updated`. If the file's `revision` on disk is no longer what you read, do not overwrite — write `<name>.conflict.md` with your content and tell the user in one sentence.
5. **Human notes are untouchable.** When rewriting a file, copy `## Notes (human)` verbatim from the existing file. Never edit, reorder, summarise or delete it. If the human wrote something there that changes your work, treat it as user input — act on it in your sections, leave theirs alone.
6. **Cite your input.** `input` names the file(s) and revision(s) you read. If the Director marks your file `stale` (the input changed), you do nothing until the user says "redo".
7. **Templates are the definition.** Fill the template from `templates/`. Keep every section heading, in order. A section that does not apply gets the line "not relevant for this idea" — never delete it. Remove the `<!-- -->` guidance comments and the `<…>` placeholders in the finished file.
8. **Nothing disappears.** An idea that is merged, split, parked or rejected keeps its ID, its file and a recorded reason. IDs are never reused. Card relations (merged into, split into, variant of, from) are recorded in the card index of `00-idea.md` by the Director and in the new card's Relation line.
9. **Relations propagate staleness.** A source card with a newer revision than a merge card cites → the merge card is `stale`, then its evaluation, then the shortlist. A variant consumed by a later operation → its umbrella is `stale`. The Director checks this at every `start`/`next` (also mid-conversation) and before every stage, and writes `stale` into the index before asking anything. Relations in the index are appended, never replaced.

## 5. Conversation rules

- **One question at a time.** Never stack questions.
- **Language.** Skill text is English. Talk to the user in the language they use (German: informal "du"). Result files are written in the language set in `00-idea.md` (`language`), resolved by the Director: English by default → profile → the language the user writes in → an explicit statement by the user. Template headings and frontmatter values stay English regardless.
- **Opening line.** Each stage starts with two sentences: what this stage produces and roughly how long it takes. No lecture.
- **Evidence marks.** Facts the user gives are tagged `[evidenced]` (in a document), `[estimated]` (from conversation) or `[unknown]`. Never fill a gap with your own guess; `[unknown]` is a valid answer.
- **Estimates are not commitments.** Say it at the start of evaluate and repeat it whenever someone hesitates over a number — otherwise you get cautious, useless numbers.
- **Opportunity language.** "Process with improvement potential", "still open", "would need clarifying" — never "broken", "bad", "unrealistic". A red light is a condition to be met, not a defect.
- **No judgment while collecting.** Critique and feasibility doubts voiced during collect are parked and resurface in evaluate. Judgment has its own stage.
- **Anonymise.** Sensitive statements about people are never attributed to named persons in any file. Contradictions are recorded as anonymised views, never smoothed over.
- **Off the record.** Anything the user marks off-record stays out of every file unless they promote it. Never promise that the platform keeps no logs.
- **Stop anytime.** On "stop", "enough", "that's it for today": write the file with whatever exists, mark unfinished sections "open", set `status: in_progress`, hand back to the Director. Never argue for continuing. Two sketches are a valid result.
- **Time budget.** `budget_min` in `00-idea.md` gives your minutes per session. When you reach it, say so and offer to close with the current state. Do not silently run over.
- **Inline first, file last.** Show interim results as formatted text in the chat. Write result files at the end of the stage (or on stop) — not continuously. Cards are the exception: write each card when it is first captured, so nothing is lost on an abrupt stop.
- **No hidden actions.** Say what you are about to write or run before you do it.

## 6. Git

Git is optional and never created by a skill. `git` in `00-idea.md` is `yes` only if the workspace (or a parent) is a git repository at start; skills never run `git init`. `yes` also requires that the work folder is tracked: a clone of the public idea repo ignores `ideas/` via `.gitignore`, so a clone counts as `no` — the Director checks with `git check-ignore`. With `git: no`, every commit step is skipped.

With `git: yes`, a commit marks a **frozen state, never progress**:

| Event | What is committed | Message |
| --- | --- | --- |
| a card reaches `status: done` (evaluation-ready) | that card | `idea(<code>): card <ID> done` |
| a card operation is confirmed | the new card(s) + `00-idea.md` | `idea(<code>): <consolidate|umbrella|split> <source IDs> → <new IDs>` |
| an evaluation reaches `status: done` | that evaluation | `idea(<code>): eval <ID> done` |
| the shortlist reaches `status: done` | `10-shortlist.md` + `00-idea.md` | `idea(<code>): shortlist done` |
| a session ends with sketches only | the sketches + `00-idea.md` | `idea(<code>): session <date> — <n> sketches` |

Skills never push, rebase or branch. Whether `planning/` is committed at all is the project's decision.

## 7. Handing back to the Director

At the end of a stage, the stage skill reports in one short block: files written (names, revisions), status (`done` proposed / `in_progress`), minutes used, open questions count. Only the Director sets `status: done` and updates `00-idea.md`.

## 8. Profile

A workspace may contain a `profile/` folder with customer-specific constraints. **The profile format is owned by the setup skill** (skill-suite-setup, design §5); this skillset only reads it. The Director reads `profile/profile.md` at every start and passes the files it names to the stages. **A profile may restrict, never loosen:** write rules, git behaviour and "nothing outside the workspace" stay as defined here. An absent or empty `profile/` means core defaults.

Files this skillset reads: `profile.md`, `questions.md`, `scope.md` (departments, topic limits, company goals → Strategy link), `standards.md` (norms with contacts for V8, effort classes for V6), `import-formats.md` (the customer's own card formats for collect's import mode).

**`profile/questions.md`** tailors the questions listed in `QUESTIONS.md` by ID:

- `skip <ID>` with a value — the stage shows the value as prefilled ("from your profile: …"), lets the user correct it once, records the answer in its result file; the profile itself is never edited.
- `add after <ID>` with a question — asked exactly once per stage run, right after the named question; the answer goes into the stage's result file under the closest section, marked `(profile)`.
- Gate and safety questions (approvals, "good as it is?", stop) can never be skipped. Unknown IDs are reported at start, not silently ignored.

The Director passes the rows of the coming stage to the stage skill together with the other profile constraints (§7 hand-back names which rows were applied).
## 9. Contracts

- **H1 — out.** `10-shortlist.md` (contract `H1/2`) is the handover to maquette. H1/2 adds to H1/1: the section **Maquette order** with `next_maquette` in the frontmatter (the committee's instruction which entry is built next, and for an umbrella which variant the demo shows), the **Relation** line and the **Variants** table per entry. A reader of H1/1 ignores the additions. Every entry is self-contained: card verbatim, evaluation, handover block. maquette ≥ 0.6.0 proposes the entry named under Maquette order and lets the user confirm or pick another — always exactly one; maquette 0.4–0.5 lists the entries and lets the user pick. Either way sparring prefills from the chosen entry. After `done`, the shortlist is not edited — a new committee round writes `10-shortlist.v2.md`.
- **Foreign cards — in.** Ideas that arrive in another format (a spreadsheet, a list, another tool's export) enter through idea-collect's import step, which maps them onto `cards/` and marks what the format could not answer `[unknown]`. The mapping used is recorded in `00-idea.md` so the next import of the same format needs no questions.
