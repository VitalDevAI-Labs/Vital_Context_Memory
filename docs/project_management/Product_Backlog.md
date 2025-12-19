# Product Backlog (Template)

> **Use this document to park every feature or enhancement that is approved conceptually but not yet scheduled.** It keeps `Implementation.md` focused on the current release and gives `Active_Task.md` a clean input queue when a new stage begins.

---

## 1. Document Purpose
- Centralize future-ready work streams across all PRD epics.
- Preserve prioritization rationale, dependencies, and acceptance hints.
- Serve as the handoff artifact when a feature graduates into `Active_Task.md`.

**Flow Reminder**
```
PRD ideas ➜ Groomed & approved ➜ Product_Backlog (this file)
      ⤷ Selected for next stage ➜ Active_Task.md ➜ Implementation.md
```

---

## 2. How to Maintain This File
1. **Intake:** After PRD changes or stakeholder input, capture the candidate feature under the correct epic.
2. **Qualify:** Document user value, effort estimate, dependencies, and definition of ready.
3. **Prioritize:** Rank items within each epic using a shared scoring model (e.g., RICE, MoSCoW).
4. **Promote:** When leadership green-lights a feature for the upcoming stage, move the entry to `Active_Task.md` and note the promotion here.
5. **Archive:** Once a feature ships, archive or remove it from this backlog to avoid double work.

Update cadence: **weekly or per sprint planning**, whichever happens first.

---

## 3. Backlog Snapshot

| Epic | Feature | Stage | Priority | Status | Notes |
|------|---------|-------|----------|--------|-------|
| `<Epic identifier>` | `<Feature name>` | Discovery / Ready / Blocked | High/Med/Low | Idea / Groomed / Approved | `<Key callouts>` |

> This table mirrors the high-level kanban state for stakeholders. Keep it short; details live in the sections below.

---

## 4. Feature Entry Template

Duplicate the block below for each backlog item. Keep the inline comments—they explain what each field is for and help automation later.

```yaml
- id: PB-000
  epic: "<PRD epic name>"
  title: "Outcome-oriented feature name"
  problem: >
    Summarize the user pain or business opportunity this feature addresses.
  audience: ["Primary persona", "Secondary persona"]
  hypothesis: >
    What we believe will improve if we ship this feature.
  user_value:
    - "Value statement #1"
    - "Value statement #2"
  acceptance_hints:
    - "Condition that must be true to call the feature complete."
  dependencies:
    technical: ["API redesign", "Vendor approval"]
    design: ["New component spec"]
    compliance: []
  effort_estimate: "S / M / L"   # optional story points or T-shirt sizing
  priority_score:
    method: "RICE"
    score: 0
  stage_readiness:
    definition_of_ready:
      - "Persona, problem, and metric validated"
      - "Design spike complete"
    blockers: []
  promotion_history: [] # Log when the feature moves to Active_Task or Implementation
  notes: >
    Link to research, stakeholder approvals, or Slack threads for extra context.
```

Group features under headings like `## Epic 1 – Contextual Notifications` to keep the document scannable.

---

## 5. Prioritization Guidance

- **RICE:** Reach × Impact × Confidence ÷ Effort. Document each component explicitly when possible.
- **MoSCoW:** Must / Should / Could / Won’t for the current planning horizon.
- **Cost of Delay:** Highlight regulatory deadlines, contractual obligations, or user churn risks.

Whichever model you use, apply it consistently and store the calculation in the `priority_score` field above so future reviewers can re-run the math.

---

## 6. Definition of Ready (DoR)
Before promoting a backlog item into `Active_Task.md`, confirm:
- [ ] Persona, problem, and success metric traced back to PRD.
- [ ] UX exploration complete or scheduled with capacity.
- [ ] Technical spike or architecture notes exist in `.acontext/decisions` if needed.
- [ ] Dependencies acknowledged with owners and tentative dates.
- [ ] Acceptance criteria clear enough for automation + manual validation.

If any item fails the DoR checklist, keep it here and document missing pieces in `blockers`.

---

## 7. Ideas Under Consideration
Reserve this section for unvetted concepts so they don’t clutter the main backlog.

```
- idea: "What if..."
  source: "Customer interview / Internal brainstorm"
  next_step: "Run discovery interview", "Prototype"
  owner: "Name"
  due: YYYY-MM-DD
```

Once an idea is validated, convert it into the Feature Entry Template and place it under the correct epic.

---

## 8. Audit Trail
Maintain a mini changelog to capture major prioritization decisions.

| Date | Change | Reason | Author |
|------|--------|--------|--------|
| `2025-12-10` | Example: Moved PB-014 to Active_Task Stage 3 | `Stakeholder sign-off` | `Product Lead` |

---

### Usage Checklist
- [ ] Every backlog entry references a PRD epic and persona.
- [ ] Implementation.md does **not** mention features that remain here.
- [ ] Active_Task.md only contains items promoted from this backlog (with recorded reason).
- [ ] Blocked items name an owner responsible for clearing the path.
- [ ] The backlog table never exceeds a manageable size (archive old entries).

Keep this document lightweight but consistently structured so agents can immediately tell what’s planned, what’s blocked, and what’s ready to promote when the next BMAD cycle begins.
