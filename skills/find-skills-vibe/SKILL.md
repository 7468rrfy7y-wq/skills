---
name: find-skills-vibe
description: Find, vet, install and adapt agent skills for vibe coders (people who build by talking to AI, often without reading code or English). Use when the user asks "is there a skill for X", "find/install a skill", when they get frustrated by the same AI mistake twice (fake "done", missed edits, ignored instructions), or before starting a new kind of task. Always reports in the user's own language, installs for them, builds a custom skill when none fits, and only says "done" after a verified before/after table.
---

# Find Skills — Vibe Coding Edition

Built on the idea of `find-skills` (vercel-labs/skills, #1 on skills.sh), adapted for **vibe coders** in **any country and any language**.

Vibe coders build by describing what they want (often by voice). Many cannot read code, and many do not read English. This skill makes skill discovery work for them.

## Core rules (always)

1. **Speak the user's language.** Detect it from how they write or talk to you. Every report, table, question and explanation is in that language. Translate skill names into a short meaning in their language, keep the original in parentheses. Explain jargon in plain words.
2. **Match the user's vibe-coding style.** Notice how they work and adapt:
   - Voice input / short messages → short replies, one question at most.
   - Does not code → never ask them to type or run commands. You run them.
   - Prefers tables / lists / step cards → use that.
   - Their recurring frustrations are the most valuable input. Turn them into rules.
3. **Never say "done" without checking.** Installing or writing a skill is not "done". Done = applied to a real task and verified (Step 8).
4. **Ask before installing.** Show what you found, then ask "Install it?" in their language.

## When to use
- "Is there a skill for …?", "find me a skill", "find it on GitHub and install it"
- The user is annoyed by the same AI behavior twice or more (claims of completion that weren't true, edits not applied, instructions forgotten, same bug repeated)
- Starting a new kind of work (design, tests, deploy, video, docs, data …)

## Step 1 — Turn the need into one line
Rewrite the user's words, including the frustration, as: "A skill that makes the AI ___ when ___ ." If it is unclear, ask **one** short question.

## Step 2 — Check what they already have
Look at the user's installed / self-made skills first. If one almost fits, propose improving it instead of installing a stranger's skill. Principle: **your own skill beats someone else's.**

## Step 3 — Search
1. Check the skills.sh leaderboard (sorted by installs) for the domain.
2. If you can run commands: `npx skills find <english keywords>`. Translate the user's need into 2–3 English keyword sets and search each.
3. If you cannot run commands: web search `skills.sh <keywords>` and GitHub `SKILL.md <keywords>`.
4. Keep at most 5 candidates.

## Step 4 — Vet before recommending (mandatory)
- Prefer 1,000+ installs, official or reputable sources, starred repos.
- **Read the whole SKILL.md** (and any scripts) before recommending. Mark as risky and do not recommend if it:
  - pipes downloads straight into a shell (`curl | bash`, `wget | sh`), or `eval`s remote code
  - reads or sends passwords, API keys, tokens, cookies
  - deletes files or changes system settings without asking
  - sends data to unknown external addresses
- Flag anything that conflicts with the user's own rules or skills.

## Step 5 — Report in the user's language (one table)

| # | Skill (meaning in user's language) | What it does (plain words) | Installs | Source | Risk | Pick |
|---|---|---|---|---|---|---|

Then one line: "My pick is #_, because ___." Then ask whether to install. Do not show raw commands as homework.

## Step 6 — Install and adapt (after approval)
- If you can run commands, install it yourself: `npx skills add <owner/repo> --skill <name> -g -y`.
- If you cannot (e.g. chat apps), fetch the skill and offer to save a **copy translated into the user's language**: translate explanations and rules, keep commands and code exactly as they are, credit the original source at the top.
- Add the user's own frustrations as extra rules in the copy, so the skill fits *their* way of vibe coding.

## Step 7 — Nothing fits? Build it
- Combine the useful parts of several candidates into one new skill.
- Put the user's frustrations in as explicit rules (e.g. "never say done for something you did not check").
- Credit every source you borrowed from.
- Write the description so the AI reads this skill **before** starting that kind of work.
- Write it in the user's language unless they want English.

## Step 8 — Prove it worked: before / after table
Apply the skill to a real task, compare with the previous run, and report:

| Item | Before | After | How I checked |
|---|---|---|---|
| "Done" report | said without checking | said after checking | opened the file / ran it |
| User's instruction applied | | | |
| Same mistake repeated | | | |

List what you verified and what you could not verify. If anything is unverified, say "applied, but ___ not verified yet" instead of "done".

## Never
- Hand the user commands or English text they cannot use
- Install a skill you have not read
- Install without permission
- Say "all done" without the table
