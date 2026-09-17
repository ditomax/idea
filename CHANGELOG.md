# Changelog — idea

## 0.2.3 — 2026-09-17
README: section order aligned with maquette and build (For agents · overview · The suite · Contracts · Structure · Inside a project · Distribution · Profiles · Language · Git · Release · Origin · License). Text unchanged. No contract change. The company abbreviation DMBG is gone from the public texts: the product is simply the skill suite (idea → maquette → build); source credits in `ATTRIBUTION.md` name Dietmar Millinger.

## 0.2.2 — 2026-09-17
Fixes from field test run-03 (ChatGPT/Codex). idea-merge: mandatory **read-back gate** before every write — conflict table (M4, never resolved silently), Variants/allocation table (M6), complete card incl. frontmatter; two new anti-patterns. Director: consistency checks on every start/next (also mid-conversation) and before every stage, `stale` written to the index before asking; relations are appended, never replaced (`from: …; merged into …`); after a redo `current: <file>@<rev>` in the Note column; all overlap groups named in one line. RULES §3: `input` paths relative to the work folder; §4.9 sharpened. idea-evaluate: card currency check before the round (stale cards not offered), evaluation written as `in_progress` before a merge hand-back once a field is confirmed, one complete entry for every ranked card (parked included, never duplicated under Parked / rejected), rubber-stamping note. Shortlist template: comments on Entries, Parked / rejected, verbatim prefill list, `input` with cards and evaluations. No contract change (H1/2).

## 0.2.1 — 2026-09-17
Discoverability: README gains § The suite (links to idea, maquette, build and skill-suite-setup, one line each, pointer to the `planning/` form for multi-skillset or customer use); § For agents no longer tells agents to ignore skill-suite-setup — point 3 names it as the producer of the `planning/` form, point 4 keeps only `hooks/` and `guard.py` as developer-only. README § Chat tools names `setup.py prompt` as the self-service route to the collect prompt file; START points plain-chat users to it; skill-suite-setup called "the suite's setup tool" instead of "the maintainers' tool". No contract change.

## 0.2.0 — 2026-09-17
**New stage skill `idea-merge` (consolidator)** with three card operations: consolidate (n → 1, sources consumed), umbrella (n → 1, sources stay active as variants), split (1 → n, source consumed). Always a new ID, source cards never edited, several groups per run, nesting allowed, exclusive consumption, provenance per line (`← <ID>`), conflicts kept as Views, strictest personal-data value. Runs between collect and evaluate or inside a committee round (evaluate hands back, Director returns). Director: merge/split words, Relation column in the card index, `superseded` evaluations, staleness propagation from sources to merge cards (RULES §4.9). Card template: Relation line, Variants section, `source: merge|umbrella|split`. Questions M1–M6 and S7.
**Contract H1/2** (additive to H1/1): shortlist section **Maquette order** + `next_maquette` frontmatter (the committee's instruction which entry maquette builds next and which variant an umbrella demo shows), Relation line and Variants table per entry, consumed cards under "Parked / rejected". maquette ≥ 0.6.0 reads it fully; older maquette reads it as H1/1.

## 0.1.5 — 2026-09-16
Consistency fix: README documents the same optional dev symlink (`skills/idea*`) as maquette/build instead of denying symlinks outright; German-only language aside removed, its content folded into the English text (a customer-variant concern, not the base README's); Release section gained the "Repository: … releases at …" line, matching maquette/build. No contract change.

## 0.1.4 — 2026-09-16
Onboarding: README § For agents (clone/ZIP, folder default, layout choice), AGENTS.md guard for subfolder and no-local-copy cases, START fallback names the folder. Director: git `yes` only if the work folder is tracked (a clone counts as no); `examples/` with fictitious finished results (Example GmbH). Templates: shortlist ranking gains a Decision column (H1/1 additive); evaluation Origin gains `estimated (moderator)`; card Views line stays with "—" instead of being omitted. Director: `status: done` bumps revision (§4.4); honest handover sentence for standalone maquette. No contract change.

## 0.1.3 — 2026-09-16
Documentation: prerequisites, chaining to maquette by naming the shortlist, profile pointer to skill-suite-setup/PROFILE.md with a minimal example, compatibility line, QUESTIONS.md in the structure, update and uninstall notes. No contract change.

## 0.1.2 — 2026-09-16
RULES §8 profile reading incl. `profile/questions.md` (skip / add by QUESTIONS.md ID); Director reads it. QUESTIONS.md IDs declared stable.

## 0.1.1 — 2026-09-15
Shortlist "Prefill for sparring" gains three lines (field of application ← V4, guardrail ← V7, premise ← "what would tip it"). Contract H1/1 unchanged. Customer references removed from examples.

## 0.1.0 — 2026-09-14
First version: workspace, Director, idea-collect (interview, collector and import modes), idea-evaluate (V1–V10, K.o. gates by estimate or waiver), templates, contract H1/1.
