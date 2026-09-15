# idea — Start in three steps

idea helps you find out where AI could support your daily work — and helps a committee decide which of those ideas deserve a prototype. You need no finished idea and no technical knowledge: you answer questions, the AI listens, models and writes everything down as readable text files in this folder.

**This folder contains only text files. No programs, no installation, no internet access.**

## 1. Put the folder somewhere

Unzip the file and place the `idea` folder where you will find it again. Do not rename it, do not delete anything inside.

## 2. Open the folder in your AI app

- **ChatGPT app (Codex):** choose Codex mode → "Open project" → select this folder.
- **Claude (Cowork):** new task → connect folder → select this folder.
- **Claude Code / Codex in a terminal:** change into the folder and start the program.

The app reads the rules from this folder automatically when it opens it.

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

## What happens with the shortlist?

The shortlist is what the next tool, **maquette**, reads: it takes one idea from the list and turns it into a clickable model in half a day. Open the maquette folder, type "start", and it finds the shortlist by itself.

## If something does not work

- The AI does not react to "start"? Type: "Read AGENTS.md and begin."
- A second department? Type: "New workspace." The first one is kept.
- New version of idea? Download the latest ZIP from https://github.com/ditomax/idea/releases, copy your `ideas/` subfolder across, done.

Version: see file `VERSION`. Questions and feedback: dietmar@millinger.at
