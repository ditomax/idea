# idea

**From "we should do something with AI" to a ranked shortlist — two markdown skills, one folder.**

Version: see `VERSION` · September 2026 · DMBG · https://github.com/ditomax/idea

_Deutsch: Für Anwender genügt `START.md` — drei Schritte, keine Installation. Gespräch und Ergebnisdateien folgen Ihrer Sprache; die Überschriften in den Vorlagen bleiben englisch._

## For agents

If you are reading this from a link and have no local copy yet:

1. Get one — `git clone https://github.com/ditomax/idea` or unzip the latest release from https://github.com/ditomax/idea/releases — into a folder the user chooses (default: `./idea` next to their other work). That download is the only network access; the "no network" rule in `AGENTS.md` applies from then on.
2. Work from inside that folder and read its `AGENTS.md`. Do not act as the Director from this README — the rules live in `RULES.md` and `skills/`.
3. Layout: standalone (this folder as is) unless the user has a project with a `planning/` folder — then the suite belongs at `planning/suite/idea/` and `planning/AGENTS.md` is the entry point, not this file.
4. A clone gives updates via `git pull`; the user's work in `ideas/` is ignored by git, so nothing of it is ever committed to a clone. `hooks/`, `guard.py` and `skill-suite-setup` are for skillset developers — ignore them.

## What it does

idea is the first of three skillsets — **idea → maquette → build** — that take an organisation from a vague wish to a shipped product without anyone re-explaining what an earlier step already established. This one finds and evaluates ideas:

| Stage | "Team member" | Who sits at the table | Result | approx. |
| --- | --- | --- | --- | --- |
| 1 collect | interviewer | one employee (solo), or one collector who interviews colleagues, or an import of existing ideas | `cards/<ID>-card.md` — one idea card per idea, evaluation-ready but unscored | 45 min per session, 3–5 cards |
| 2 evaluate | committee moderator | a committee, one writer at the keyboard | `evaluations/<ID>-eval.md` per card and `10-shortlist.md` — ranked, with reasons | 30 min per card, 30 min for the shortlist |

Finished results look like the files in `examples/` — one card, its evaluation and a two-entry shortlist for a fictitious company. A Director skill (`idea`) reads the folder, tells the user where they stand, and calls the stage. The user types `start`, then **next**, **redo** or **stop**.

Collect never judges; evaluate never generates. That separation is the method: the interview surfaces pains before technology, the committee assesses concept maturity — never the person, never the idea — with ten fields, K.o. gates and an index anyone can recompute by hand. Where a K.o. field is unknown, the committee estimates or waives; ideas are never sent back and never silently dropped.

## Contracts

- **Out — H1.** `10-shortlist.md` (contract `H1/1`) is read by maquette (≥ 0.4.0; ≥ 0.5.0 also uses V4, V7 and "what would tip it"): the user picks exactly one entry, and maquette's sparring stage prefills from it instead of asking again. Every entry is self-contained.
- **In — foreign cards.** Ideas that already exist in a spreadsheet or another tool enter through collect's import step, mapped onto cards with the gaps marked `[unknown]`; the mapping is remembered per format.

Both seams are optional. maquette also starts from an idea in prose; idea also works without maquette.

**Compatibility.** Out: `10-shortlist.md` is contract `H1/1`, read by maquette ≥ 0.4.0. In: none (foreign cards enter through collect's import). Version triples tested together are listed in [skill-suite-setup/compat.md](https://github.com/ditomax/skill-suite-setup/blob/main/compat.md). Changes: `CHANGELOG.md`.

## Structure

```
idea/
  START.md             three steps for the human
  AGENTS.md            entry point for Codex — turns the agent into the Director
  CLAUDE.md            the same for Claude
  VERSION
  README.md            this file
  RULES.md             shared rules for both stages — frontmatter, write rules, conversation rules, git, contracts
  QUESTIONS.md         every question the skillset asks, with stable IDs — the tailoring surface for profiles
  CHANGELOG.md         what changed per version
  hooks/               pre-commit guard for development clones (see Release)
  ATTRIBUTION.md       where the method comes from
  profile/             optional customer-specific constraints (empty = core defaults)
  examples/            fictitious finished results — a card, an evaluation, a shortlist (Example GmbH)
  ideas/               the users' work, one subfolder per organisation (not in the repo)
  templates/           one template per result file (binding content definition)
    00-idea.md         control file
    card.md            idea card
    evaluation.md      ten-field evaluation
    10-shortlist.md    handover to maquette (contract H1/1)
  skills/
    idea/              Director
    idea-collect/
    idea-evaluate/
```

## Inside a project

The workspace above is the standalone form. Inside a project folder the suite is copied to `planning/suite/idea/` (read-only), the work lives in `planning/idea/`, the profile in `planning/profile/`. maquette and build sit next to it under the same `planning/`. The Director recognises the layout by the `planning/` folder — nothing to configure.

## Distribution and installation

This folder is the workspace — repo and ZIP have the same structure. Users download the ZIP of a release, unzip it, open the folder in their AI app and type "start" (see `START.md`). `AGENTS.md` (Codex) and `CLAUDE.md` (Claude) are read automatically and make the agent the Director — nothing to install, no symlinks, no global skill folders.

Developers who want the skills globally can additionally:

```
ln -s "$PWD/skills/"idea* ~/.codex/skills/      # or ~/.claude/skills/
```

No dependencies, no network access, no telemetry. `ideas/` is excluded from the repo via `.gitignore`.

**Chat tools without folder access** (plain ChatGPT, Le Chat, Perplexity): the collect stage of idea can run there as a single prompt file — ask us for it (produced with skill-suite-setup). The other stages need a folder.

## Profiles

Customer-specific variants (restricted topics, IT constraints, standards, corporate design, the customer's own review process, questions skipped or added) do not fork this repo. They live in a `profile/` folder the Director reads at start; a profile may restrict, never loosen. The format is specified in [skill-suite-setup/PROFILE.md](https://github.com/ditomax/skill-suite-setup/blob/main/PROFILE.md); a minimal example is in `profile/README.md`. `QUESTIONS.md` lists every question the skillset asks, with stable IDs — read it before a session, and use the IDs in a profile to skip or add questions.

## Language

All skill text, template headings, frontmatter keys and status values are English. The conversation follows the user's language (German → informal "du"). The language of the result files is resolved by the Director: English by default → profile → the language the user writes in → an explicit statement by the user ("I write German, the cards shall be English").

## Git

Optional. Skills never create a repository; if one exists, a commit marks a frozen state (a card done, an evaluation done, the shortlist done) and nothing else — the policy is in `RULES.md` §6.

## Release

Development clones activate the customer-data guard once: `git config core.hooksPath hooks` (the hook calls `guard.py` from the sibling `skill-suite-setup` repo and blocks commits that carry customer markers). Release ZIPs are built with `skill-suite-setup/release.py`, which ships only git-tracked, allowlisted, guard-clean files.

New version: bump `VERSION`, tag `vX.Y.Z`, GitHub release with the folder attached as `idea-vX.Y.Z.zip`. Users update by downloading the new folder and copying their `ideas/` (and `profile/`) across.

## Origin

collect merges our `ki-ideenfindung` (interview method for mid-sized companies, idea card) and `idea-work` (mode discipline, elicitation toolkit, pre-mortem). evaluate is our `konzeptskizze` skill and the Kriterienkatalog Konzeptbewertung v0.3 — ten fields, K.o. gates, index and confidence unchanged — moved from a one-on-one to a committee setting. See `ATTRIBUTION.md`.

## License

MIT — see `LICENSE`.
