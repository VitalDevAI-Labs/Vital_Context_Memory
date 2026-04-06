# Project Context

<!-- AGENT INSTRUCTIONS: This is your entry point for every task. -->
<!-- Read this file first. Then follow the orchestration rules below to know exactly -->
<!-- which files to read next and which to update when you're done. -->

## Project

- **Name:** `[PROJECT_NAME]`
- **Description:** `[One-line description of what this project does]`
- **Stack:** `[e.g., React Native / Node.js / SQLite]`

## Current Stage

- **Stage:** `[e.g., Stage 1 - Core Experience]`
- **Objective:** `[What this stage delivers]`
- **Status:** `[Not started / In progress / Complete]`
- **Exit Criteria:** `[How we know this stage is done]`

## Phases

| # | Phase | Goal | Status |
|---|-------|------|--------|
| 0 | `[Foundations]` | `[Repo, CI, scaffolding]` | `[done/active/pending]` |
| 1 | `[Core Experience]` | `[Smallest value slice]` | |
| 2 | `[Expansion]` | `[Secondary flows, integrations]` | |
| 3 | `[Polish & Hardening]` | `[Bug fixes, perf, telemetry]` | |
| 4 | `[Launch]` | `[Deploy, monitor, iterate]` | |

## Active Tasks

| ID | Task | Requirements | Status | Owner |
|----|------|--------------|--------|-------|
| `task-YYYYMMDD-NNN` | `[title]` | `[REQ IDs]` | `planned/active/done` | `[name]` |

## Key Decisions

| # | Decision | Choice | Why |
|---|----------|--------|-----|
| 1 | `[e.g., Framework]` | `[React]` | `[rationale]` |
| 2 | `[e.g., Database]` | `[Firebase]` | `[rationale]` |
| 3 | `[e.g., Hosting]` | `[Vercel]` | `[rationale]` |

Full decision log with alternatives in [architecture.md](architecture.md).

## Key Rules

- **File placement:** Follow `rules/structure.md` when creating new files or directories
- **Naming:** `[e.g., camelCase for files, PascalCase for components, kebab-case for routes]`
- **UI work:** Follow `rules/design.md` for colors, components, spacing, and accessibility
- **Bugs:** Check `bugs.md` before investigating any issue — it may already be documented

---

## Orchestration Rules

> These rules tell you exactly what to read and what to update for every type of work.
> Follow them on every task — don't read more than needed, don't skip updates.

### Starting a Task

**Read before you start:**
- This file (done) — you know the stage, active tasks, and decisions
- `tasks/index.md` — check if similar work was done before to avoid duplication
- Then follow the rules below based on task type

**Create before you implement:**
- `tasks/task-YYYYMMDD-NNN-[name].md` — goal, plan, requirements being addressed

---

### By Task Type — What to Read

| Task Type | Read These Files |
|-----------|-----------------|
| **Feature / UI work** | `rules/structure.md`, `rules/design.md`, `architecture.md` (data models + endpoints) |
| **API / backend work** | `architecture.md` (full), `rules/structure.md` |
| **Bug fix** | `bugs.md` first, then `architecture.md` for the affected flow |
| **Architecture decision** | `architecture.md` (Key Decisions — check if already decided) |
| **Planning next stage** | `PRD.md`, `playbook.md`, `backlog.md` |
| **Resume previous work** | `tasks/task-[ID].md` for the specific task log |
| **Checking requirements** | `PRD.md` §7 (Requirements Registry) |
| **New component / module** | `rules/structure.md`, `rules/design.md` |
| **Deploy / environment** | `reference.md` (commands, env vars) |

---

### By Task Type — What to Update When Done

| Task Type | Update These Files |
|-----------|--------------------|
| **Any task** | `tasks/task-[ID].md` (log outcome), `tasks/index.md` (status), this file (Active Tasks) |
| **Feature complete** | `PRD.md` §7 (mark requirements done), `playbook.md` (check off DoD items) |
| **Bug fixed** | `bugs.md` (add resolution), task log |
| **Architecture decision** | `architecture.md` (Key Decisions table), this file (Key Decisions summary) |
| **Schema / data model changed** | `architecture.md` (Data Models), `reference.md` (Key Collections table) |
| **New API endpoint** | `architecture.md` (API Endpoints), `reference.md` (Quick Lookup) |
| **New file / folder created** | `rules/structure.md` (if pattern changes), `reference.md` (File Structure) |
| **New env var** | `reference.md` (Environment Variables table) |
| **Stage complete** | `playbook.md` (mark AC + DoD done, fill Hand-off), this file (Phases table + Current Stage) |
| **New requirement discovered** | `PRD.md` §7 (Requirements Inbox), then assign ID + stage |
| **Backlog item promoted** | `backlog.md` (remove), `CONTEXT.md` Active Tasks (add), `playbook.md` (add to stage) |

---

### Completing a Stage — Checklist

Before marking a stage done, verify:
- [ ] All requirements for this stage are `done` in `PRD.md` §7
- [ ] All Acceptance Criteria checked in `playbook.md`
- [ ] All Definition of Done items checked in `playbook.md`
- [ ] Hand-off note written in `playbook.md` (what the next stage inherits)
- [ ] This file's Phases table updated to `done`
- [ ] Current Stage section updated to the next stage
- [ ] Active Tasks table refreshed with next stage tasks

---

## Reference Docs

| Doc | Purpose |
|-----|---------|
| [PRD.md](PRD.md) | Product vision, epics, features, requirements registry (§7) |
| [playbook.md](playbook.md) | Stage goals, requirements, acceptance criteria, Definition of Done |
| [architecture.md](architecture.md) | Stack, schemas, data flows, API endpoints, decisions |
| [reference.md](reference.md) | Commands, env vars, file structure, quick lookups |
| [rules/structure.md](rules/structure.md) | File organization, naming conventions, module boundaries |
| [rules/design.md](rules/design.md) | Colors, typography, spacing, components, accessibility |
| [bugs.md](bugs.md) | Known issues and resolutions |
| [backlog.md](backlog.md) | Deferred features and future ideas |
| [tasks/index.md](tasks/index.md) | All task history — check before starting similar work |
