---
name: web-design-guidelines-vibe
description: "Web page UI / accessibility / UX check for vibe coders. The AI finds the page files itself, checks them against Vercel's Web Interface Guidelines, and posts a plain-language report in the user's language. Use when the user says, in any language, e.g. \"check my page design\", \"review accessibility\", \"화면 점검해 줘\", \"접근성 봐 줘\", \"画面をチェックして\", \"检查网页设计\", \"revisa el diseño de mi página\", \"vérifie mon site\", \"prüf meine Webseite\"."
---
<!--
Vibe-coding adaptation of `web-design-guidelines` from vercel-labs/agent-skills
Original: MIT License, Copyright (c) 2025 Vercel Labs
Rules source: github.com/vercel-labs/web-interface-guidelines (command.md)
Adapted with adapt-skills-vibe (github.com/7468rrfy7y-wq/skills): user's language, background execution, verified report.
-->

# Web Design Check — Vibe Coding Edition

## Rules
- Report in the user's language, in plain words. Add the code location (`file:line`) once, in parentheses.
- Do not ask the user which files to check. Find the HTML / CSS / JS / component files in the project yourself. If there are many, start with the pages real visitors see.
- Use the latest rules from `https://raw.githubusercontent.com/vercel-labs/web-interface-guidelines/main/command.md` (or `git clone https://github.com/vercel-labs/web-interface-guidelines`). If you cannot get them, use the last copy you have and say so in the report.
- If the page is not in English, skip English-only copy rules (Title Case, curly quotes, etc.) and say they were skipped.
- Check only. Do not change any file until the user asks you to fix something.

## Steps
1. Find the page files to check.
2. Get the latest rules.
3. Read the files and check every rule.
4. Post the report below. If there is a work folder, also save it as `REPORT-<date>.md`.

## Report format (in the user's language)
```
✅ What I did
🔴 Must fix        — problem → who it affects → how to fix (one line each)
🟡 Nice to fix
🟢 Already good
🔍 Verified        — what you actually read/checked
⚠️ Not verified    — e.g. real phone screen, screen reader test
➡️ Next step       — e.g. "Say 'fix it' and I'll fix the must-fix items and re-check with a before/after table"
```
- Anything checked only by reading code (not on a real screen or with a screen reader) goes under "Not verified".
- If the user then asks to fix: fix, re-run this check, and show a before/after table. Never say "done" without it.
