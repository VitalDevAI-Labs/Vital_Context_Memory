# Product Requirements Document

> Defines **what** the product must deliver. Keep it solution-agnostic — no file paths or tech choices here. Update this doc first when scope changes, then cascade to `CONTEXT.md`.

---

## Document Meta

| Field | Value |
|-------|-------|
| **Product Name** | `[Product Name]` |
| **Version** | `1.0` |
| **Owner** | `[Product lead]` |
| **Status** | Draft / In Review / Approved |
| **Last Updated** | `YYYY-MM-DD` |

---

## 1. Product Overview

- **What:** `[One sentence — what this product does]`
- **Why:** `[The problem it solves]`
- **Who:** `[Target users]`

---

## 2. Personas

```
### Persona N – [Role]
- **Profile:** [Environment, responsibilities, constraints]
- **Goals:** [What outcome they chase]
- **Frictions:** [Pain points today]
- **Success:** [How they know the product helps]
```

---

## 3. Problem Statements

For each problem: **Who** experiences it, **when/where**, **what** breaks, **why** it matters now.

| # | Problem | Who | Urgency |
|---|---------|-----|---------|
| 1 | `[description]` | `[persona]` | Critical / Important / Emerging |

---

## 4. Goals & Success Metrics

| Metric | Baseline | Target | Notes |
|--------|----------|--------|-------|
| `[e.g., task completion rate]` | `[current]` | `[goal]` | |

Keep under 6 metrics. Note if new telemetry is required.

---

## 5. Scope

### In Scope (Current Release)
- `[Epic/feature 1]`
- `[Epic/feature 2]`

### Out of Scope
- `[Deferred item]` → tracked in [backlog.md](backlog.md)

### Assumptions & Constraints
- `[Platform, regulatory, resource constraints]`

---

## 6. Epics & Features

```
### Epic N: [Name]
- **Persona:** [Who benefits]
- **Problem:** [Link to §3]
- **Outcome:** [Observable change]
- **Features:**
  1. [Feature] — [user value]
     - Success: [testable condition, e.g., "loads in <2s", "works offline"]
     - Dependencies: [APIs, libraries, services needed]
  2. [Feature] — [user value]
     - Success: [testable condition]
     - Dependencies: [what it needs]
- **Overall Success Criteria:** [How we know the epic works as a whole]
- **Risks:** [Unknowns or platform constraints]
```

Include per-feature success criteria so agents can self-validate. List dependencies so agents know what to import/configure. For domain-specific specs (alert strategies, sync intervals, permission flows), add subsections under the relevant feature.

Tag each epic: `MVP` / `Future` / `Research`.

---

## 7. Experience Scenarios

| Scenario | Trigger | Steps | Happy Path | Edge Cases |
|----------|---------|-------|------------|------------|
| `[name]` | `[start condition]` | `[steps]` | `[success]` | `[failures]` |

---

## 8. Risks & Open Questions

| ID | Risk / Question | Severity | Owner | Mitigation |
|----|-----------------|----------|-------|------------|
| R-01 | `[description]` | High/Med/Low | `[name]` | `[plan]` |

---

## Checklist
- [ ] Every epic links to a persona + problem statement
- [ ] Out-of-scope items tracked in `backlog.md`
- [ ] Success metrics are measurable
- [ ] No implementation specifics in this doc
