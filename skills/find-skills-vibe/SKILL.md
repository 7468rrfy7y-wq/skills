---
name: find-skills-vibe
description: "Find, vet, install and adapt agent skills for vibe coders (people who build by talking to AI, often without reading code or English). Use when the user asks for a skill in any language, e.g. \"find skills vibe\", \"vibe coding skill finder\", \"바이브코딩 스킬 찾기\", \"バイブコーディング スキル探し\", \"氛围编程 找技能\", \"buscar skills vibe coding\", \"procurar skills vibe coding\", \"chercher des skills vibe coding\", \"Vibe-Coding Skills finden\", \"वाइब कोडिंग स्किल खोजो\", \"tìm skill vibe coding\", \"cari skill vibe coding\", \"ابحث عن مهارة برمجة\"; or when they get frustrated by the same AI mistake twice (fake \"done\", missed edits, ignored instructions). Replies in the user's language, installs for them, builds a custom skill when none fits, and only says \"done\" after a verified before/after table."
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
- **Proactively, at the start of any new task or project** (an app, a page, a video, a document, a deployment …) — even if the user did not ask. Vibe coders often don't know which skills exist, so they can't ask for them. Run Step 0.
- "Is there a skill for …?", "find me a skill", "find it on GitHub and install it"
- The user is annoyed by the same AI behavior twice or more (claims of completion that weren't true, edits not applied, instructions forgotten, same bug repeated)
- Starting a new kind of work (design, tests, deploy, video, docs, data …)

## Step 0 — Proactive recommendations (engineer-level, vibe-ready)
At the start of a new task, before doing the work:
1. Ask yourself: "What skills would a professional engineer use for this task?" (e.g. testing, accessibility review, security check, performance, deployment, code review, design system, SEO).
2. Search for them (Step 3) and vet them (Step 4). Keep the best 3–7.
3. Post one summary in the user's language. Start with this line, translated into the user's language:

   **"Skills that only professional engineers could use are now available to you through vibe coding."**

   Then one table:

   | # | Skill (meaning in user's language) | What engineers use it for | What it does for you (plain words) | Installs | Source | Risk |
   |---|---|---|---|---|---|---|

   Then: "My top pick for this task is #_, because ___. Install? (I'll make it vibe-ready and run it in the background.)"
4. Keep it to one short message. Do not block the task: if the user ignores it, continue the work.
5. Do not repeat the same recommendations for the same project; only recommend again when the task changes.
6. When the user picks skills: install them (Step 6) and hand developer-style ones to `adapt-skills-vibe`.

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
- If the skill is written for developers (tells the user to run commands, read code, edit configs) and `adapt-skills-vibe` is installed, hand it over to `adapt-skills-vibe` right away so it becomes vibe-ready (background execution + verified report). If it is not installed, offer to install it from `7468rrfy7y-wq/skills`.

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
