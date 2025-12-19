# Implementation Plan (Developer + Agent Friendly)

> Bridge from PRD/Product_Backlog to execution. Shows what is in-scope this cycle, which stage we are in, and how to finish it. Keep IDs aligned with `Product_Backlog` and `Active_Task`.

---

## Document Meta

| Field | Value |
|-------|-------|
| **Product / Initiative** | `<Name>` |
| **Current Cycle** | `<Cycle identifier or date range>` |
| **Version** | `<SemVer or incremental number>` |
| **Owner** | `<Tech/Product lead>` |
| **Status** | Draft / In Progress / Signed Off |
| **Last Updated** | `YYYY-MM-DD` |
| **Linked Docs** | `PRD.md`, `Product_Backlog.md`, `Active_Task.md`, `.acontext/tasks` |

---

## 1) Scope Alignment (this cycle)
- List the PRD epics/features included now, plus what is explicitly out.

| PRD Epic | Included Features | Deferred To | Notes |
|----------|------------------|-------------|-------|
| `<Epic>` | `<Bulleted list>` | `Product_Backlog` / `Future cycle` | `<Reason / metric>` |

Call out exclusions to prevent scope creep.

---

## 2) Stack (only what matters this cycle)

| Layer | Tech | Version | Notes |
|-------|------|---------|-------|
| Mobile | `<RN/Flutter/etc>` | | |
| Backend | `<Node/Rails/etc>` | | |
| Data | `<SQLite/Postgres>` | | |
| Notifications | `<Service/Adapter>` | | |
| Monitoring | `<Axiom/Sentry/etc>` | | |

Add research spikes before locking choices.

---

## 3) Stage Blueprint

| Stage | Objective | Key Deliverables | Exit Criteria |
|-------|-----------|------------------|---------------|
| Stage 0 — Foundations | Environments, CI/CD, base arch | Repo setup, lint/test harness, base theme | All devs can build & test locally. |
| Stage 1 — Core Experience | Ship smallest value slice | Core user journeys, baseline data layer | Acceptance criteria validated end-to-end. |
| Stage 2 — Expansion | Add depth (notifications, automation) | Secondary flows, integrations | MVP feature completeness. |
| Stage 3 — Polish & Hardening | Close gaps, add telemetry | Bug backlog, perf tuning | Release candidate approved. |
| Stage 4 — Launch & Feedback | Final QA, rollout | Release notes, KPIs dashboard | MVP live + monitoring active. |

Adjust stages as needed; keep exit criteria explicit.

---

## 4) Stage Playbook (duplicate per active stage)

```
### Stage <Number>: <Name>
- Window: <Dates or sprints>
- Goals: <Measurable outcomes>
- Key Tasks: Active_Task IDs (link) + brief notes.
- Dependencies: Teams/vendors/decisions required.
- Acceptance Criteria: How we know the stage is done.
- Risks & Mitigations: Stage-specific issues.
- Hand-off: What to record in `.acontext/tasks` + Implementation summary.
```

Keep completed stages at the bottom as history.

---

## 5) Research & Validation (pre-implementation)
- Discovery tasks (interviews, log analysis, benchmarks).
- Tech spikes with success criteria/owners.
- Decision links: `.acontext/decisions/*` when finalized.

---

## 6) Quality & Verification
- Testing pyramid for this cycle (unit/integration/e2e).
- Manual QA scenarios/devices/data.
- Monitoring/alerts tied to Stage 3/4 criteria.
- Definition of Done (DoD):
  - Tests written & passing.
  - Accessibility verified (if UI).
  - Feature flags/config documented.
  - Telemetry/dashboards updated.
  - Task log in `.acontext` completed + linked in `Active_Task.md`.

---

## 7) Risks

| ID | Description | Stage Impacted | Owner | Mitigation / Trigger |
|----|-------------|----------------|-------|----------------------|
| R-01 | `<Risk>` | `<Stage>` | `<Owner>` | `<Plan>` |

Keep lean; move resolved items to `.acontext/decisions` if reusable.

---

## 8) Working Agreements
- Stand-up cadence/channel.
- Branching + code review rules.
- Doc expectations (every PR links Active_Task ID + task log).
- Escalation path for blockers.

---

## 9) Change Management
- Scope changes: approval path + PRD/Product_Backlog updates.
- Emergency work: where to log hotfixes so they don’t bypass BMAD docs.
- Versioning: when to snapshot this file (e.g., end of each stage) and how to reference prior versions.

---

## 10) Stage Summary Archive
```
### Stage N Summary
- Dates:
- What shipped:
- Evidence: links to demos/metrics/`.acontext/tasks`.
- Lessons Learned:
- Follow-ups: moved to Product_Backlog or Active_Task.
```

---

### Usage Checklist
- [ ] Every stage here maps to `Active_Task.md` entries.
- [ ] No feature listed unless it traces back to `PRD.md`.
- [ ] Research tasks have owners + success criteria.
- [ ] DoD/quality align with `project_structure.md` guidance.
- [ ] Risks have owners + mitigation hooks.

Keep this concise and current so agents can align instantly.
