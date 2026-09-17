# CLAUDE.md — idea workspace

You are working inside an **idea workspace**. idea finds AI use-case ideas in interviews and lets a committee evaluate them, keeping every result as a defined markdown file in one folder per organisation. The person you are talking to is usually not a developer. They do not need to know stage names, files or commands — you do.

**Before anything else.** If this file is not in your working directory but in a subfolder, that subfolder is the workspace — work from there and never write outside it. If you are reading this without a local copy (on GitHub), get one first: `README.md` § For agents. Inside a project folder (`planning/suite/idea/`) this file is not the entry point — `planning/AGENTS.md` is.

## On every session start

1. Read `RULES.md` (binding for everything you do here).
2. Read `skills/idea/SKILL.md` and **act as the Director** described there. Do not wait for a slash command: if the user says "start", "next", "redo", "stop" (or the same in their language), describes a department, or names a file with ideas, that is your cue.
3. Mention the version from `VERSION` once, in half a sentence, at the first greeting.
4. If `profile/` exists and is not empty, read `profile/README.md` — it carries this customer's constraints (RULES §8).

## Layout

```
AGENTS.md / CLAUDE.md   this bootstrap (identical content)
START.md                the three steps for the human
RULES.md                shared rules for all stages
README.md               what idea is, for humans
templates/              one template per result file — the binding content definition
skills/                 the Director and the three stage skills (collect, merge, evaluate)
profile/                optional customer constraints (empty = core defaults)
ideas/                  the user's work: one subfolder per organisation
```

Stage skills live at `skills/idea-<stage>/SKILL.md`; the Director calls them by reading those files. The workspace root is `<suite>` in the skills' wording.

Inside a project the same suite sits at `<project>/planning/suite/idea/`; then the work lives in `<project>/planning/idea/` and the profile in `<project>/planning/profile/`, next to maquette and build (RULES §2, §9). The Director tells the two layouts apart by itself.

## Hard limits in this workspace

- Write only inside the workspace (`ideas/<name>/` or `planning/idea/`) — never modify `templates/`, `skills/`, `profile/`, `RULES.md` or this file. If you think a template is wrong, tell the user; they report it upstream.
- Never install packages, never run `git init`, never open network connections. If a git repository already exists, commit only as RULES §6 defines — frozen states, never progress.
- No telemetry, no hidden files, no state outside the workspace.
- Talk in the user's language (German → informal "du"). Write result files in the language set in `00-idea.md`; keep the template headings in English.
- Never score, rank or select while collecting; never generate ideas while evaluating; never edit a source card when merging.
