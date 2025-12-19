# Project Structure & Conventions (Template)

> **This document defines where every file lives and how to name, organize, and test code in a BMAD-driven project.** Keep it alongside `Implementation.md` so agents can build new modules without guesswork. Replace `<examples>` with project specifics while leaving the commentary intact for future readers.

---

## 1. Purpose
- Provide a deterministic directory layout so agents know exactly where to create or edit files.
- Capture naming conventions, import aliases, and lint rules to minimize code review friction.
- Serve as the canonical reference for `AGENT_WORKFLOW.md` when it says “Check project_structure”.

---

## 2. Repository Overview

```
root/
├─ Docs/
│  ├─ PRD.md
│  ├─ Implementation.md
│  ├─ Product_Backlog.md
│  ├─ Active_Task.md
│  └─ ...
├─ apps/ or packages/ (optional monorepo layout)
├─ src/
│  ├─ app/              # Navigation, root providers
│  ├─ components/       # Reusable UI atoms/molecules
│  ├─ hooks/            # Shared React hooks
│  ├─ screens/          # Route-level components
│  ├─ services/         # Network + platform services
│  ├─ store/            # State management (Zustand/Redux/etc.)
│  ├─ theme/            # Typography, colors, spacing tokens
│  ├─ types/            # TypeScript definitions
│  ├─ utils/            # Pure helper functions
│  └─ __tests__/        # Unit + integration tests
├─ scripts/             # Automation scripts (lint, release, etc.)
├─ .acontext/           # Task logs + execution memory
└─ ...
```

Adjust the tree to match your stack but keep the categories (components/services/store/etc.) so new contributors can orient themselves quickly.

---

## 3. Naming Conventions

| Item | Convention | Example |
|------|------------|---------|
| Files (TS/JS) | `camelCase` for helpers, `PascalCase` for React components | `formatDate.ts`, `TaskCard.tsx` |
| Directories | `kebab-case` unless framework enforces otherwise | `task-detail` |
| Types / Interfaces | `PascalCase` suffix with `Props`, `Response`, etc. | `AlarmPayload`, `TaskListProps` |
| Tests | Mirror source path + `.test.ts` / `.spec.ts` | `components/TaskCard.test.tsx` |
| Assets | `kebab-case` descriptive names | `primary-gradient.png` |

**Prefix conventions**
- Hooks: `useTaskStore.ts`
- Zustand slices: `<domain>.slice.ts`
- Services: `<domain>Service.ts`

---

## 4. Module Boundaries

### Components vs Screens
- **components/** contains reusable units with zero routing knowledge.
- **screens/** map to navigation routes and compose components + data fetching hooks.

### Services
- Encapsulate IO (API, storage, notifications). Keep them pure functions returning promises.
- No component imports allowed inside services. If a service needs UI feedback, emit events/state updates instead.

### State Store
- Centralize app state in `/store`. Keep persistence adapters (AsyncStorage, IndexedDB) in `/services` and inject them into store initialization.

---

## 5. Import Paths & Order

Add aliases in `tsconfig.json` or relevant tooling to avoid long relative paths:
```
@app/*         → src/app/*
@components/*  → src/components/*
@screens/*     → src/screens/*
@services/*    → src/services/*
@store/*       → src/store/*
@types/*       → src/types/*
@utils/*       → src/utils/*
@theme/*       → src/theme/*
```

**Import order (top ➜ bottom):**
1. Node/polyfill modules.
2. Third-party packages.
3. Absolute aliases (`@app`, `@components`, …).
4. Relative paths.
5. Styles/assets.

Use lint rules (`eslint-plugin-import`) to enforce this automatically.

---

## 6. Testing Layout

```
src/
  __tests__/          # Pure functions, hooks, utilities
  screens/__tests__/  # Screen-level integration tests
  services/__tests__/ # Service contract tests
  e2e/                # Detox/Playwright/etc.
```

- Co-locate snapshot tests with their components when it helps readability.
- For feature work, aim for: `unit tests + integration tests + e2e happy path`.
- Document any required mocks in `.acontext/artifacts` if they influence future debugging.

---

## 7. Styling & Theming
- A central `src/theme/` module exports tokens (colors, spacing, typography). No hard-coded hex values outside this folder.
- Components import tokens via theme hooks or helper functions.
- Dark/Light mode switches live at the app provider layer (`src/app/themeProvider.tsx`).

---

## 8. Platform Guidelines

| Concern | Guidance |
|---------|----------|
| **Native Modules** | Add bridging files under `native/` or `ios/android` directories; document in `.acontext/artifacts`. |
| **Background Work** | Place scheduler logic in `src/services/background/`. Keep platform-specific wrappers isolated. |
| **Permissions** | Store permission helpers in `src/services/permissions.ts` and surface user-facing copy via `UI_UX_doc.md`. |

---

## 9. Documentation Hooks
- Every new module must add a short description + location in `AGENT_WORKFLOW.md` (Section: “Where to edit or create files”).
- When introducing a new directory or alias, update this file immediately and reference the change inside `.acontext/decisions`.

---

## 10. Code Comments & Patterns
- Prefer self-documenting functions; reserve comments for non-obvious reasoning or platform quirks.
- Use TODO/FIXME tags sparingly and always include an owner or ticket reference.
- Capture complex decision making in `.acontext/decisions` rather than inline comments.

---

## 11. Git & Branching
- Branch per task (`feature/TASK-###-short-name`).
- Include doc updates (`Active_Task.md`, task logs) in the same PR as code.
- Commit message format: `feat(scope): summary (#TASK-ID)` or similar.

---

### Checklist for Contributors
- [ ] The directory you are about to touch exists in this file; if not, update the structure first.
- [ ] New files follow the naming conventions above.
- [ ] Imports respect alias order; lint locally before opening a PR.
- [ ] Tests live next to or under the module they validate.
- [ ] When refactoring structure, update this file + AGENT_WORKFLOW before merging.

This template keeps file organization intentional, enabling agents to ramp fast and reducing the “where does this go?” ping-pong during reviews.
