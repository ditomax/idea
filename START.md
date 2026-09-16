# idea — Start in three steps

idea helps you find out where AI could support your daily work — and helps a committee decide which of those ideas deserve a prototype. You need no finished idea and no technical knowledge: you answer questions, the AI listens, models and writes everything down as readable text files in this folder.

**This folder contains only text files.** Nothing is installed.

## What you need

- An AI app that can **read and write files in this folder**: ChatGPT app in Codex mode, Claude (Cowork, with the folder connected), Claude Code or Codex in a terminal, Mistral Vibe CLI. A plain chat window without folder access is not enough.
- Nothing else. A spreadsheet with existing ideas is welcome but optional.
- The skillset itself installs nothing and needs no internet access. Everything it writes stays in this folder.

## 1. Put the folder somewhere

Unzip the file and place the `idea` folder where you will find it again. You may rename the folder; keep everything inside it.

## 2. Open the folder in your AI app

- **ChatGPT app (Codex):** choose Codex mode → "Open project" → select this folder.
- **Claude (Cowork):** new task → connect folder → select this folder.
- **Claude Code / Codex / Vibe in a terminal:** change into the folder and start the program.

The app is meant to read the rules from this folder by itself. **If nothing happens after step 3, type: "Read AGENTS.md and begin."**

## 3. Type "start"

Type **start** — or simply describe your department in two sentences. If ideas already exist in a spreadsheet, say so: the AI reads them in and asks only what the spreadsheet could not answer. From then on the AI guides you and asks after each station: **next**, **redo** or **stop**. There are no other commands.

| Station | Who | What you get | approx. |
| --- | --- | --- | --- |
| 1 | Interviewer | Your ideas as cards — one per idea, with everything a committee needs, nothing judged | 45 min, 3–5 cards |
| 2 | Committee moderator | Each card assessed in ten fields, and a ranked shortlist with reasons | 30 min per card |

Station 1 is for one person at a time — you alone, or you as the one who talks to colleagues and reports back. Station 2 is for a group: one of you types, the group discusses and decides.

You can stop at any time. Whatever exists by then stays in the `ideas/` folder and continues next time with **next**.

## Where is what?

Every organisation or department gets its own subfolder in `ideas/`, for example `ideas/PMK-product-marketing/`. Inside are the cards (`cards/`), the evaluations (`evaluations/`) and the shortlist (`10-shortlist.md`). Everything opens in any text editor. At the end of every file there is a section **Notes (human)**: leave your own remarks there, the AI never touches it.

## What happens with the shortlist? (chaining)

The shortlist is what the next tool, **maquette**, reads: it takes one idea from the list and turns it into a clickable model in half a day. Two ways to hand it over:

- **Two separate folders (idea and maquette side by side):** open the maquette folder, type "start", and when it asks what to start from, say *"here is the shortlist:"* and give the path to your `10-shortlist.md` — or paste the entry you want. maquette then lists the entries, you pick one, and its first station confirms what the committee already answered instead of asking again.
- **One project folder for all three tools:** the suite can also be installed as one structure (`planning/` with all skillsets, a profile and an entry point that knows which tool is up). That structure is produced with the maintainers' tool [skill-suite-setup](https://github.com/ditomax/skill-suite-setup) — ask us for a delivery, or use the tool yourself if you are comfortable with a small Python script.

## If something does not work

- The AI does not react to "start"? Type: "Read AGENTS.md and begin."
- A second department? Type: "New workspace." The first one is kept.
- New version of idea? Download the latest ZIP from https://github.com/ditomax/idea/releases, unzip it next to the old folder, and move your work folder (`ideas/` and `profile/` if you have one) across. Work started under an older version is fine — the AI notices what changed and offers to redo a step where needed; it never fails on it. Ask us before editing a profile, so your changes survive the next version.
- Uninstall? Delete the folder. Your work is in the work folder — take it with you first.

Version: see file `VERSION`. Questions and feedback: dietmar@millinger.at
