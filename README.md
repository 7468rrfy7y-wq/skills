# Vibe skills: find-skills-vibe + adapt-skills-vibe

Skills that work together:
- **find-skills-vibe** — finds, vets and installs skills, in your language
- **adapt-skills-vibe** — turns any coding skill into a vibe-coding skill: AI does every technical step in the background, you get a verified report at the end

Install both and every skill in the open ecosystem becomes usable just by talking.

```
npx skills add 7468rrfy7y-wq/skills --all
```

---

## find-skills-vibe

**Find, vet, install and adapt agent skills — for vibe coders, in any language.**
**바이브코더를 위한 스킬 찾기 — 어느 나라 말이든 그 사람 말로.**

Inspired by `find-skills` (vercel-labs/skills). Made by a vibe coder who builds only by voice, can't read code or English.

## What it does
- **Recommends engineer-level skills on its own** when you start a task — "Skills that only professional engineers could use are now available to you through vibe coding."
- Answers in **your** language (Korean, Japanese, Spanish, Hindi … whatever you speak)
- Adapts to **your** vibe-coding style: you talk, it runs the commands
- Checks your own skills first, then searches skills.sh / GitHub
- Reads every skill before recommending it, flags risky ones
- Installs for you, or saves a translated copy you can actually read
- Nothing fits? Builds a new skill from several, with your frustrations as rules
- Never says "done" without a before/after table

## Install
```
npx skills add 7468rrfy7y-wq/skills --skill find-skills-vibe
```
Or just tell your AI: "Install the find-skills-vibe skill from github.com/7468rrfy7y-wq/skills".

## 설치 (한국어)
AI한테 이렇게 말하세요: "github.com/7468rrfy7y-wq/skills 에 있는 find-skills-vibe 스킬 깔아 줘"

## Say it in your language
Just say "vibe coding skill finder" in your own language:
바이브코딩 스킬 찾기 · バイブコーディング スキル探し · 氛围编程 找技能 · buscar skills vibe coding · procurar skills vibe coding · chercher des skills vibe coding · Vibe-Coding Skills finden · वाइब कोडिंग स्किल खोजो · tìm skill vibe coding · cari skill vibe coding · ابحث عن مهارة برمجة

## adapt-skills-vibe
- Rewrites developer instructions ("run this", "edit that") into "the AI does it and tells you"
- Keeps commands and code exactly as the original, credits the source, never overwrites it
- Asks one plain sentence only before risky steps (delete, deploy, pay, send)
- Ends every job with a before/after report in your language, saved as REPORT-<date>.md

```
npx skills add 7468rrfy7y-wq/skills --skill adapt-skills-vibe
```
한국어: AI한테 "github.com/7468rrfy7y-wq/skills 에 있는 스킬 두 개 다 깔아 줘"

## web-design-guidelines-vibe (example adapted skill)
Vercel's `web-design-guidelines` (880K+ installs) made vibe-ready with adapt-skills-vibe: the AI finds your page files, checks them, and reports in your language — problem → who it affects → how to fix.
```
npx skills add 7468rrfy7y-wq/skills --skill web-design-guidelines-vibe
```
Original: vercel-labs/agent-skills (MIT, © 2025 Vercel Labs).

## License
MIT
