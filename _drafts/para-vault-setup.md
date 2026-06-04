---
title: "The PARA setup, start to finish"
date: 2026-06-03 13:00:00 -0700
summary: "Setting up a fresh PARA vault on Obsidian this week — why the protocol is a discipline, not a system, and what the seven-step setup actually involves."
---

I have a vault on my Mac that has been my second brain for years. This week I made it a sibling: a fresh vault with a different name, an empty folder tree, a new protocol. The reason is not what you think.

I have a stack of dead systems before both: Things, Evernote, Notion, plain Markdown, three earlier Obsidian vaults that are now archives. I have done this before. The thing that made this restart different is that I didn't build it for me. I built it so the agent that lives inside my computer can read it.

PARA is a folder protocol. Four top-level categories — Projects, Areas, Resources, Archives — and a fifth if you count the Inbox. The idea is that everything in your knowledge life is one of those four things: a thing you're trying to finish, a thing you're responsible for, a thing you want to learn about, or a thing that's done. The category is the verb. The verb is the question you ask before you file a note: *is this something I'm shipping, something I'm maintaining, something I'm learning, or something I already shipped?* Once the question has an answer, the folder is no longer a decision.

```
PARAVault/
├── 0 - Inbox/        # raw captures, unprocessed
├── 1 - Projects/     # active, time-bound, has an outcome
├── 2 - Areas/        # ongoing responsibilities, no end
├── 3 - Resources/    # reference material / topics of interest
├── 4 - Archives/     # inactive, completed
├── _meta/            # system files (conventions, workflows, mumen.md)
├── agent.md          # the entry point any AI reads first
└── README.md         # human: what this is
```

The numbers are not aesthetic. They sort the folder list the way file browsers display it, so the Inbox is always at the top, and Archives is always at the bottom. The convention works.

## The parts that matter

**The Inbox.** The Inbox is the most important folder. It is where things land when they don't yet know what they are. The point of the Inbox is not to be organized. The point of the Inbox is to be emptied. There is a daily cron that runs against the Inbox and applies the triage rules: project → file it. Area → file it. Resource → file it. Finished thing → file it in Archives. The Inbox should never have more than a day or two of unprocessed material. If it does, the system is failing.

**`agent.md` at the root.** This is the file any AI agent reads first. It is the protocol map. It contains the vault purpose in one paragraph, the folder map with examples of what goes in each, the Inbox triage rules, a description of progressive disclosure (how to drill from `agent.md` → subfolder `README.md` → individual notes), a pointer to a personalization file, the frontmatter convention (`status:`, `type:`, `tags:`, `created:`), the wikilink convention `[[Note Name]]`, and a note that consolidation jobs may move or rename notes and that references are auto-fixed.

The reason this file exists is that the agent is not a person. The agent reads the whole vault top-down if you let it, which is slow and expensive. The agent needs an entry point. `agent.md` is the entry point. From there, it drills into subfolders by reading that subfolder's `README.md`, and from there it goes into individual notes as needed. The drill is on demand. The whole vault is never read.

**Per-folder `README.md`s.** Each of the five PARA folders has its own README that defines its lifecycle. Projects README: "open → active → done → moves to 4 - Archives." Areas README: "no end state. Things here are ongoing responsibilities. They don't move." Resources README: "topics of interest. Reference material. Can become Projects. Can become Archives. Doesn't move on its own." The READMEs are short. They are not the protocol. They are reminders of the protocol. The agent reads them when it needs to remember what the folder is for.

**`_meta/`.** System files that don't fit any of the four categories: a personality and vision stub (to be filled in), `conventions.md` (naming, frontmatter, wikilink rules), `workflows.md` (cron job stubs: daily triage, weekly consolidation). The leading underscore sorts the folder to the bottom of the file list, which is where system files belong.

## The setup, in order

**1. Pick a path.** The path matters. The vault lives in a Google Drive folder that syncs to my phone, my iPad, and any other Mac I happen to use. Drive is the sync layer. Drive is also the backup. Local-only would be faster to read but slower to recover from.

**2. Scaffold the folder tree.** The numbered folders, the `_meta/` directory, the `.obsidian/` config (auto-populated on first open in Obsidian), the `.gitignore` (ignore `.obsidian/workspace*`, `.trash/`, `.DS_Store`).

**3. Write the entry-point files.** `README.md` for the human. `agent.md` for the agent. Both are short. The README is a one-paragraph purpose statement plus a table of the five folders with one-line descriptions. The `agent.md` is the longer protocol map described above.

**4. Write the per-folder READMEs.** Five files, one for each folder. Lifecycle rules. Examples. The whole set takes about ten minutes.

**5. Register the vault in Obsidian.** Obsidian keeps a list of vaults in `~/Library/Application Support/obsidian/obsidian.json`. Add a new entry with a new vault ID (a UUID — generate it, don't reuse one). Obsidian picks it up on next launch and shows the new vault in the switcher.

**6. `git init` + initial commit.** Local-only, no remote. The reason is version control on the protocol itself — if I edit `agent.md` in a way that breaks a downstream skill, I want to be able to roll back. The git history is the audit log of the protocol. Once the protocol is stable, I can add a remote. Until then, local-only is enough.

**7. Open the vault once.** This is the only step I couldn't automate. Obsidian creates its `.obsidian/` config directory on first open, and it does that only when a human triggers it via the UI. After that, the URL scheme works for any cron or skill that wants to write into the vault.

## What the protocol forces me to do

PARA is not a system. It is a discipline. The discipline is in the triage, and the triage is hard. Most notes don't know what they are when I first write them. A note I write today because I had an idea might be a Project (if I commit to it), an Area (if I commit to the larger responsibility), a Resource (if I just want to remember it), or an Archive (if I already shipped it and forgot). The folder is downstream of the decision, and the decision is downstream of asking the question.

The hardest part of the protocol is the part that has nothing to do with folders. It is the daily discipline of running the Inbox. The Inbox fills up on its own. The Inbox does not empty on its own. If I don't run the daily triage, the Inbox becomes the second brain, and the second brain becomes a junk drawer, and the junk drawer becomes the system. The protocol works only if I run the cron.

That is the honest report. The setup is one weekend. The discipline is forever.
