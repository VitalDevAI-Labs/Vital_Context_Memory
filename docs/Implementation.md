# Implementation Plan (Template)

> **This document explains _how_ we are executing the subset of the PRD that is officially in scope.** It acts as the bridge between strategy (PRD + Product_Backlog) and execution memory (`Active_Task.md` + `.acontext`). Replace placeholders with project-specific details but keep the structure and inline tips.

---

## Document Meta

| Field | Value |
|-------|-------|
| **Product / Initiative** | `<Name>` |
| **Current BMAD Cycle** | `<Cycle identifier or date range>` |
| **Version** | `<SemVer or incremental number>` |
| **Owner** | `<Tech/Product lead>` |
| **Status** | Draft / In Progress / Signed Off |
| **Last Updated** | `YYYY-MM-DD` |
| **Linked Docs** | `PRD.md`, `Product_Backlog.md`, `Active_Task.md`, `.acontext/tasks` |

---

## 1. Scope Alignment
Summarize the specific PRD epics / features that this implementation cycle covers.

| PRD Epic | Included Features | Deferred To | Notes |
|----------|------------------|-------------|-------|
| `<Epic>` | `<Bulleted list>` | `Product_Backlog` / `Future cycle` | `<Reason / success metric>` |

Call out anything explicitly **not** included even if it belongs to the same epic. This prevents scope creep.

---

## 2. Technology & Tooling Stack
Document the approved stack for this cycle (keep high-level; detailed file conventions live in `project_structure.md`).

| Layer         | Technology                      | Version | Notes / Rationale |
| ------------- | ------------------------------- | ------- | ----------------- |
| Mobile        | `<React Native, Flutter, etc.>` | `X.Y.Z` | `<Why chosen>`    |
| Backend       | `<Node, Rails, etc.>`           |         |                   |
| Data          | `<SQLite, Postgres>`            |         |                   |
| Notifications | `<Firebase, Notifee>`           |         |                   |
| Monitoring    | `<Axiom, Sentry>`               |         |                   |

Add any research spikes or proof-of-concepts required before committing to the stack.

---

## 3. BMAD Stage Blueprint

Use standardized stage names to keep teams aligned. You can rename the objective column but keep the general flow from discovery → delivery → stabilization.

| Stage | Objective | Key Deliverables | Exit Criteria |
|-------|-----------|------------------|---------------|
| Stage 0 – Foundations | Environments, CI/CD, base architecture | Repo setup, lint/test harness, base theme | All developers can build & test locally. |
| Stage 1 – Core Experience | Ship the smallest slice that proves value | Core user journeys, baseline data layer | Acceptance criteria validated end-to-end. |
| Stage 2 – Expansion | Add depth (notifications, automation, etc.) | Secondary flows, integrations | Feature completeness for MVP. |
| Stage 3 – Polish & Hardening | Fix gaps, add telemetry, UX refinements | Bug backlog, performance tuning | Release candidate approved. |
| Stage 4 – Launch & Feedback | Final QA, rollout, instrumentation | Release notes, KPIs dashboard | MVP live + monitoring active. |

> Adjust or extend stages as needed, but keep an explicit exit criteria column so teams know when to move on.

---

## 4. Stage Playbooks

For each active stage, describe the plan using the template below. Duplicate the section and keep completed stages at the bottom as history.

```
### Stage <Number>: <Name>
- **Window:** `<Dates or sprint count>`
- **Goals:** `<Bullet list of measurable goals>`
- **Key Tasks:** Reference `Active_Task.md` IDs or embed a short list if the stage is just starting.
- **Dependencies:** Calls to other teams, vendors, or decisions required.
- **Acceptance Criteria:** Moment when the stage can be considered complete.
- **Risks & Mitigations:** Stage-specific issues.
- **Hand-off Instructions:** What gets moved into `.acontext/tasks` logs, and how success is recorded.
```

For stages still in planning, fill everything except `Key Tasks` until groomed tasks exist.

---

## 5. Research & Validation Work (Pre-Implementation)

- **Discovery Tasks:** Interviews, log analysis, benchmark reviews.
- **Tech Spikes:** Proof-of-concept work with success criteria and owners.
- **Decision Logs:** Link to `.acontext/decisions` entries when conclusions are made.

This section prevents research work from being forgotten or going undocumented in `Active_Task.md`.

---

## 6. Quality & Verification Strategy

- **Testing Pyramid:** Unit, integration, end-to-end breakdown with owners/tools.
- **Manual QA:** Scenarios, devices, and data sets required before release.
- **Monitoring & Alerts:** Metrics that indicate regressions (tie to Stage 3/4 acceptance criteria).
- **Definition of Done (DoD):** Checklist engineers must satisfy before marking a task as complete.

```
Definition of Done
- Tests written & passing (unit + e2e where relevant)
- Accessibility requirements verified
- Feature toggles / config documented
- Telemetry + dashboards updated
- Task log in `.acontext` completed and linked in Active_Task.md
```

---

## 7. Risk Register

| ID | Description | Stage Impacted | Owner | Mitigation / Trigger |
|----|-------------|----------------|-------|----------------------|
| R-01 | Example: “Notification vendor quota may be insufficient.” | Stage 2 | Tech Lead | Negotiate quota before Stage 2 kickoff; fallback to alternate vendor. |

Keep this table trimmed but current. Move finalized learnings into `.acontext/decisions` when resolved.

---

## 8. Working Agreements

Document the social contracts and operating rituals for the engineering/agent team:
- Stand-up cadence and medium.
- Branching + code review rules.
- Documentation expectations (e.g., “Every PR links to Active_Task ID + task log”).
- Escalation path for blockers.

> These agreements prevent knowledge drift when new agents join mid-stage.

---

## 9. Change Management
- **Scope Changes:** How additions/removals get approved (e.g., “Requires Product + Tech lead sign-off and PRD update”).
- **Emergency Work:** Where to log hotfixes so they don’t bypass BMAD documentation.
- **Versioning:** When to snapshot this file (e.g., end of each stage) and how to reference previous versions.

---

## 10. Stage Summary Archive
Once a stage completes, capture the highlights here:

```
### Stage N Summary
- Dates:
- What shipped:
- Evidence (links to demos, metrics, or `.acontext/tasks`):
- Lessons Learned:
- Follow-up items (rolled into Product_Backlog or Active_Task):
```

This acts as a lightweight postmortem log inside Implementation.md without overwhelming current readers.

---

### Usage Checklist
- [ ] Every stage listed here corresponds to entries in `Active_Task.md`.
- [ ] No feature appears here unless it traces back to `PRD.md`.
- [ ] Research tasks have success criteria and owners.
- [ ] Definition of Done + Quality strategy aligns with `project_structure.md` guidelines.
- [ ] Risks have owners and mitigation hooks—never leave blank cells.

Keep this Implementation Plan living and concise. Update it whenever scope or sequencing changes so future agents can spin up instantly with the latest direction.
