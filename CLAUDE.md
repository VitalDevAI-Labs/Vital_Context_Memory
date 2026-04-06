# CLAUDE.md

<!-- This file is auto-loaded by Claude Code every session. Keep it slim (<80 lines). -->
<!-- All project details live in .vital_context/ — this file is behavioral guardrails only. -->

## Project Brain

**Always start by reading `.vital_context/CONTEXT.md`** — it has the project state, active tasks, tech stack, and pointers to every other doc you need. Don't ask the user to re-explain the project.

For first-time setup, follow the bootstrap prompt in `.vital_context/QuickPrompts.md`.

## Agent Behavior

- **Read before writing.** Read the relevant .vital_context/ files before making changes. Don't guess at schemas, conventions, or project state.
- **Update docs as you work.** When you finish a task, update `CONTEXT.md` active tasks, `tasks/index.md`, and the task log. When you complete a requirement, update `PRD.md` §7 status. When you complete a stage, update `playbook.md`.
- **Follow the routing table.** CONTEXT.md tells you which doc to read for which type of work. Don't read everything — read what's relevant.
- **Don't re-decide decided things.** Check `architecture.md` Key Decisions before proposing alternatives. If a decision is logged, follow it unless the user explicitly wants to revisit.
- **Log what matters.** Task files should capture decisions, trade-offs, and blockers — not obvious steps. Keep logs under 30 lines.

## Security & Privacy

- `[e.g., API keys stored in .env only — never commit, never log, never hardcode]`
- `[e.g., No secrets in localStorage in production]`
- `[e.g., All external API calls go through server-side proxy — no client-side API keys]`
- `[e.g., RLS policies enforce user isolation — never bypass in queries]`

## Collaboration Model

- `[e.g., Solo developer (VitalDev) — no PR reviews needed, commit directly]`
- `[e.g., Claude Chat = planning layer, Claude Code = execution layer]`
- `[e.g., User makes architectural decisions, agent proposes and implements]`

## Key Learnings

<!-- Things learned from past projects or this project that save time and prevent mistakes. -->

- `[e.g., Notion API is reliable for personal apps but rate-limited at 3 req/sec]`
- `[e.g., Local cache dramatically improves perceived performance]`
- `[e.g., Always test on real data early — synthetic data hides edge cases]`
- `[e.g., Phased requirements keep scope manageable — don't scope Phase 3 during Phase 1]`

## Implementation Principles

- `[e.g., Start minimal — get the core loop working before adding features]`
- `[e.g., Free-tier first — Vercel + Supabase/Notion free tiers are sufficient]`
- `[e.g., Desktop-first, mobile via PWA — don't optimize for mobile until Phase 3]`
- `[e.g., No backend complexity unless strictly needed — prefer direct API calls]`

## Gotchas

<!-- Quick warnings that save the agent from common mistakes in this project. -->

- `[e.g., Notion API requires Notion-Version header — always include '2022-06-28']`
- `[e.g., shadcn/ui components must be installed individually — npx shadcn-ui@latest add button]`
- `[e.g., Tailwind classes won't work if not included in content paths in tailwind.config]`
- `[e.g., CORS proxy needed for Notion API in dev — see reference.md for setup]`

## Quick Reference

| Need | File |
|------|------|
| Project state & active tasks | `.vital_context/CONTEXT.md` |
| Requirements & IDs | `.vital_context/PRD.md` §7 |
| Stage progress & DoD | `.vital_context/playbook.md` |
| Schemas, APIs, decisions | `.vital_context/architecture.md` |
| Commands, env vars, file map | `.vital_context/reference.md` |
| File/naming conventions | `.vital_context/rules/structure.md` |
| UI/design system | `.vital_context/rules/design.md` |
| Task history | `.vital_context/tasks/index.md` |
| Known bugs | `.vital_context/bugs.md` |
| Future work | `.vital_context/backlog.md` |
| Prompts & workflows | `.vital_context/QuickPrompts.md` |
