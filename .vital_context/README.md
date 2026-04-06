# Vital Context Framework

A lightweight documentation system that makes any project AI-agent-friendly. Two layers: CLAUDE.md (behavioral guardrails, auto-loaded) + .vital_context/ (structured project brain, on-demand).

## Quick Start

1. Copy `.vital_context/` folder and `CLAUDE.md` into your project root
2. Run the bootstrap prompt from `.vital_context/QuickPrompts.md` to fill all files
3. Review and correct the output

That's it. Claude Code auto-reads `CLAUDE.md` every session, which points to `.vital_context/CONTEXT.md` for project state. The agent knows what to read, what to build, and what to update.

## How It Works

```
CLAUDE.md (auto-loaded every session, ~60 lines)
├── Behavioral rules for the agent
├── Security & privacy constraints
├── Key learnings & gotchas
└── Pointer → .vital_context/CONTEXT.md

.vital_context/CONTEXT.md (loaded on-demand per task)
├── Project state, active tasks, current phase
└── Routing table → deeper docs only when needed
```

**CLAUDE.md** = how the agent should behave (always loaded, free context)
**CONTEXT.md** = what the project is and what to do (loaded per task, structured)

## Structure

```
project-root/
├── CLAUDE.md               # Auto-loaded by Claude Code. Behavioral guardrails + pointer to .vital_context/
├── .vital_context/
│   ├── CONTEXT.md          # THE entry point. Agents read this first and only this per task.
│   ├── README.md           # You're reading it.
│   ├── playbook.md         # Stage-level progress, acceptance criteria, DoD, hand-offs
│   ├── QuickPrompts.md     # Universal prompts, bootstrap prompt, workflows
├── PRD.md              # Product requirements & detailed feature specs
├── architecture.md     # Stack, schemas, data flows, API endpoints, decisions
│   ├── reference.md        # Commands, env vars, file structure, quick lookups
│   ├── backlog.md          # Future work & ideas
│   ├── bugs.md             # Known issues & resolutions
│   ├── rules/
│   │   ├── structure.md    # File organization & naming conventions
│   │   └── design.md       # UI/UX design system & components
│   └── tasks/
│       ├── index.md        # Task registry + lightweight log template
│       └── task-*.md       # Individual task logs (~20 lines each)
```

## Philosophy

- **Two layers** — `CLAUDE.md` for behavior (auto-loaded), `.vital_context/` for project state (on-demand)
- **One file per task** — agents read `CONTEXT.md`, nothing else unless directed
- **No ceremony** — task logs are ~20 lines, not 120
- **Self-maintaining** — agents update docs as they work (tasks, requirements, playbook)
- **Read on demand** — deeper docs (PRD, rules, bugs) are reference material, not prerequisites
