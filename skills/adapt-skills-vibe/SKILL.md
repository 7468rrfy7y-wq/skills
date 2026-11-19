---
name: adapt-skills-vibe
description: "Turn any developer/coding skill into a vibe-coding skill: the AI runs every technical step in the background, the user only talks, and every job ends with a verified report in the user's language. Use right after find-skills-vibe installs a skill, when a skill tells the user to type commands, read code or edit config files, or when the user asks in any language, e.g. \"adapt skill for vibe coding\", \"바이브코딩용으로 바꿔 줘\", \"バイブコーディング用に変えて\", \"改成氛围编程用\", \"adaptar skill para vibe coding\", \"adapter le skill au vibe coding\", \"Skill für Vibe-Coding anpassen\", \"वाइब कोडिंग के लिए बदलो\", \"chuyển skill sang vibe coding\", \"ubah skill untuk vibe coding\"."
---

# Adapt Skills — Vibe Coding Edition

Most skills are written for developers: "run this command", "open this file", "edit the config". Vibe coders build by talking (often by voice), may not read code or English, and should never be handed homework.

This skill rewrites a coding skill so that **the AI does all technical work in the background** and **the user gets a clear report at the end**. Pairs with `find-skills-vibe`: that one finds and installs skills, this one makes them vibe-ready.

## Core rules (always)
1. **User's language.** Every question, update and report is in the language the user speaks. Plain words, no unexplained jargon.
2. **Background execution.** Anything technical (commands, code, files, configs, builds, tests) is done by the AI. Never tell the user to type, paste, open or edit something technical.
3. **One-line asks only for risky steps.** Deleting data, deploying/publishing, paying, sending messages, changing accounts or security: ask once in one plain sentence, then continue.
4. **No fake "done".** "Done" only after checking the result for real (Step 5). Otherwise say what is not verified yet.
5. **Keep the original working.** Commands, code, file paths and flags stay exactly as in the original skill. Only who-does-it and how-it's-explained change.

## When to use
- `find-skills-vibe` just installed a skill (run this automatically on it)
- A skill contains user-facing instructions like "run", "type", "copy", "open the terminal", "edit the file", "check the logs"
- The user says a skill is too technical, or asks to adapt one

## Step 1 — Read the original skill fully
Read SKILL.md and any scripts/references. List every place where the **user** is expected to act or understand something technical.

## Step 2 — Rewrite (make a vibe copy, never overwrite the original)
Create a copy named `<original-name>-vibe` and change:

| Original says | Vibe copy says |
|---|---|
| "Run `npm test`" | "Run `npm test` yourself and report the result in plain words" |
| "Open X and edit Y" | "Edit Y in X yourself; tell the user what changed in one line" |
| "Check the logs / output" | "Read the logs yourself; report only what matters and what to do" |
| "Ask the user for the API key / config value" | "Look for it in the project first; ask in one plain sentence only if missing; never ask for passwords" |
| Jargon in explanations | Plain words in the user's language (keep the term in parentheses once) |
| Risky step without warning | One-line confirmation before it |

Add at the top of the copy:
- Source and license of the original (credit it)
- "Follow the rules of adapt-skills-vibe: user's language, background execution, verified report"

## Step 3 — Show the change (one table, user's language)

| Part of the skill | Before (for developers) | After (for vibe coders) |
|---|---|---|

Then ask once: "Use the vibe version from now on?" If yes, install/enable the copy so it is used instead of the original.

## Step 4 — Do the work in the background
When the vibe copy is used on a real task: run every step yourself. While working, give at most short one-line updates if the task is long. No raw logs, no code dumps unless asked.

## Step 5 — Verify, then report
Check the result for real: open the file, run it, load the page, run the tests, compare with before. Then post the **completion report** in the user's language:

```
✅ What I did:   (1–3 lines, plain words)
📋 Before / After
| Item | Before | After | How I checked |
|---|---|---|---|
🔍 Verified:     (list)
⚠️ Not verified: (list, or "none")
➡️ Next step:    (one suggestion, optional)
```

- If a project/work folder exists, also save the report there as `REPORT-<date>.md`, so it can be found later.
- If anything is in "Not verified", do not use the word "done"; say "applied, but ___ is not verified yet".

## With find-skills-vibe
find-skills-vibe finds → vets → installs → **adapt-skills-vibe makes it vibe-ready** → the work runs in the background → **verified report**. Together, any skill in the open ecosystem becomes usable just by talking.

## Never
- Hand the user commands, code or config to run themselves
- Change what the original skill actually does (only who does it and how it is explained)
- Overwrite the original skill
- Report "done" without the before/after table
