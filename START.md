# idea — Start in three steps

## For AI agents

*People: skip this section — your guide starts at "What you need" below.*

This page is the guide for humans. If someone hands it to you:

- **Asked to start or use idea** → read `AGENTS.md` in the same folder as this file (the root of the repository or release), then the files it names for the start. Work from those, not from this page.
- **Asked only to explain or check this file** → answer the question; do not start the workflow.
- **A local folder is open** → work with its files. **Only a GitHub link** → read the files you need from the same branch or release as this file. Reading a link does not set up a working folder. The working folder is a **project folder on the user's computer that the user can see and open** — not a copy in your own sandbox; `AGENTS.md` says how to get one.
- **Files or write access are missing** → say which step is missing (for example: "unzip the release and open that folder in your app, with write access") instead of working around it.
- The workflow rules live in `AGENTS.md` and the files it names; this page does not repeat them.

idea helps you find out where AI could support your daily work — and helps a committee decide which of those ideas deserve a prototype. You need no finished idea and no technical knowledge: you answer questions, the AI listens, models and writes everything down as readable text files in this folder.

**This folder contains only text files.** Nothing is installed.

## What you need

- An AI app that can **read and write files in this folder**: ChatGPT app in Codex mode, Claude (Cowork, with the folder connected), Claude Code or Codex in a terminal, Mistral Vibe CLI. A plain chat window without folder access is not enough — except for collecting ideas, which also runs there as a single prompt file (see README, *Chat tools without folder access*).
- Nothing else. A spreadsheet with existing ideas is welcome but optional.
- The skillset itself installs nothing and needs no internet access. Everything it writes stays in this folder.

## 1. Put the folder somewhere

Unzip the file and place the `idea` folder where you will find it again. You may rename the folder; keep everything inside it.

## 2. Open the folder in your AI app

- **ChatGPT app (Codex):** choose Codex mode → "Open project" → select this folder.
- **Claude (Cowork):** new task → connect folder → select this folder.
- **Claude Code / Codex / Vibe in a terminal:** change into the folder and start the program.

The app is meant to read the rules from this folder by itself. **If nothing happens after step 3, type: "Read AGENTS.md in the folder that contains START.md and begin."**

## 3. Type "start"

Type **start** — or simply describe your department in two sentences. If ideas already exist in a spreadsheet, say so: the AI reads them in and asks only what the spreadsheet could not answer. From then on the AI guides you and asks after each station: **next**, **redo** or **stop**. There are no other commands.

| Station | Who | What you get | approx. |
| --- | --- | --- | --- |
| 1 | Interviewer | Your ideas as cards — one per idea, with everything a committee needs, nothing judged | 45 min, 3–5 cards |
| (between) | Consolidator | Optional: cards that belong together become one card, one card with two ideas becomes two — say "merge" or "split"; the originals are kept | 15 min |
| 2 | Committee moderator | Each card assessed in ten fields, and a ranked shortlist with reasons | 30 min per card |

**The project is already fixed?** Say so after "start" — for example "we know what we want to build, we want to hear everyone first". Then the stations are different: first the project is described once, then each perspective (a person, a role, or a returned mail) contributes what the product must achieve, respect and never do; the AI joins everything into one list — duplicates together, contradictions side by side, nothing lost — and a committee checks the project, decides the contradictions and marks what is a must. The result is one prioritised register instead of a shortlist.

Station 1 is for one person at a time — you alone, or you as the one who talks to colleagues and reports back. Station 2 is for a group: one of you types, the group discusses and decides.

You can stop at any time. Whatever exists by then stays in the `ideas/` folder and continues next time with **next**.

## Where is what?

Every organisation or department gets its own subfolder in `ideas/`, for example `ideas/PMK-product-marketing/`. Inside are the cards (`cards/`), the evaluations (`evaluations/`) and the shortlist (`10-shortlist.md`). Everything opens in any text editor. At the end of every file there is a section **Notes (human)**: leave your own remarks there, the AI never touches it.

## What happens with the shortlist? (chaining)

The shortlist is what the next tool, **maquette**, reads: it takes one idea from the list and turns it into a clickable model in half a day. Two ways to hand it over:

- **Two separate folders (idea and maquette side by side):** open the maquette folder, type "start", and when it asks what to start from, say *"here is the shortlist:"* and give the path to your `10-shortlist.md` — or paste the entry you want. maquette then proposes the entry the committee chose for the next maquette (or lists the entries), you confirm or pick one, and its first station confirms what the committee already answered instead of asking again.
- **One project folder for all three tools:** the suite can also be installed as one structure (`planning/` with all skillsets, a profile and an entry point that knows which tool is up). That structure is produced with the suite's setup tool [skill-suite-setup](https://github.com/ditomax/skill-suite-setup) — ask us for a delivery, or use the tool yourself if you are comfortable with a small Python script.

## If something does not work

- The AI does not react to "start"? Type: "Read AGENTS.md in the folder that contains START.md and begin."
- A second department? Type: "New workspace." The first one is kept.
- New version of idea? Download the latest ZIP from https://github.com/ditomax/idea/releases, unzip it next to the old folder, and move your work folder (`ideas/` and `profile/` if you have one) across. Work started under an older version is fine — the AI notices what changed and offers to redo a step where needed; it never fails on it. Ask us before editing a profile, so your changes survive the next version.
- Uninstall? Delete the folder. Your work is in the work folder — take it with you first.

Version: see file `VERSION`. Questions and feedback: dietmar@millinger.at
