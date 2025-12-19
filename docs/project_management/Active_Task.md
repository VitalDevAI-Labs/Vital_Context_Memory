# Active Tasks Reference

This document is a reusable template for the **Active Tasks** layer inside any BMAD + AContext repository. It acts as the groomed sprint backlog for the **current implementation stage** and sits between the strategic backlog (`Product_Backlog.md`) and the execution trails (`Implementation.md` + `.acontext/tasks`). Copy it into each project repo, then customize the live data while keeping the explanation comments for future teams.

---

## 1. Purpose
- Create a **single queue of ready-to-build tasks** that already passed through discovery and backlog vetting.
- Mark the **exact point where Product strategy hands work to Engineering**.
- Maintain real-time visibility into **status, ownership, dependencies, estimates, and acceptance criteria**.
- Act as the canonical reference for what developers/agents should be working on today.

**Task journey**
```
PRD → Product_Backlog → Active_Tasks → Implementation → .acontext/tasks → Code
```

---

## 2. How To Use This File
1. **At Stage Kickoff**  
   - Review PRD + Product_Backlog.  
   - Break the current Implementation stage into 4–10 atomic tasks.  
   - Paste each task into the table + YAML entry below.
2. **During Execution**  
   - Update `status`, `actual_hours`, and `notes` daily.  
   - Link each task to its `.acontext/tasks/...` log once started.  
   - Move completed tasks into `Implementation.md`’s “Completed This Stage” list.
3. **After Stage Completion**  
   - Archive the task list (keep for reference).  
   - Reset the table with the next stage’s groomed tasks.

---

## 3. Dashboard Snapshot

| Stage | Owner | Tasks Ready | In Progress | Blocked | Done | % Complete | Notes |
|-------|-------|-------------|-------------|---------|------|------------|-------|
| `<Stage Name>` | `<Product/Tech Lead>` | `<#>` | `<#>` | `<#>` | `<#>` | `<auto or manual>` | `<call out risks or scope changes>` |

> Update the snapshot whenever task counts change. This gives a one-glance summary for leads without opening every task entry.

---

## 4. Task Entry Template

Use the YAML block below for each task. Keep the comments—they explain why each field matters. When a task starts, copy the `task_log_path` into the `.acontext/tasks` index so execution history is linked.

```yaml
- id: TASK-000
  title: "Concise action statement"
  summary: >
    One-paragraph description focusing on the outcome, not implementation.
  status: not-started | in-progress | blocked | ready-for-review | completed
  priority: high | medium | low
  related_epic: "PRD Epic reference"
  stage: "Implementation stage label (e.g., Stage 2 – Alarm System)"
  type: feature | research | bugfix | enablement
  estimated_hours: 4
  actual_hours: null # fill when done
  owner: "Person or agent currently responsible"
  start_date: null   # ISO date when actual work begins
  due_date: null     # Optional, only if sprint has deadlines
  dependencies:
    - TASK-000 # keep empty array if none
  blockers: []        # describe what's blocking + owner
  context_links:
    prd: "PRD.md#L123"        # direct anchor/line references help future readers
    backlog: "Product_Backlog.md#L75"
    implementation: "Implementation.md#L210"
    research: null
  acceptance_criteria:
    - "Specific, testable condition #1"
    - "Specific, testable condition #2"
  deliverables:
    - path: "src/services/example.ts"
      note: "New file"
    - path: "docs/sequence-diagram.png"
      note: "Updated artifact"
  validation:
    manual: "Describe manual QA steps"
    automated: "Tests to run (unit/e2e)"
  communication_plan:
    cadence: "Daily async update in channel"
    stakeholders: ["Designer", "QA"]
  task_log_path: ".acontext/tasks/task-YYYYMMDD-XXX-descriptor.md"
  notes: >
    Free-form observations, reminders, or rationale decisions. Keep short and link
    longer write-ups to task logs.
```

Add each task entry under a `tasks:` list to keep valid YAML if you want automation support. Otherwise, treat each entry as a stand-alone block.

---

## 5. Grooming Checklist

- [ ] Confirm every task traces to a PRD epic + Implementation stage.
- [ ] Break down work so each task fits in **2–8 hours** of flow time.
- [ ] Define **acceptance criteria** that are binary (pass/fail).
- [ ] Identify dependencies early so blocking tasks stay ahead in the queue.
- [ ] Set owners only when work actually begins to avoid stale assignments.
- [ ] Keep **estimates + actuals** close—if they diverge, capture the reason in notes.
- [ ] Link every running task to an `.acontext/tasks` log and update daily.

---

## 6. Status Definitions

- `not-started`: Groomed and ready; no work yet.
- `in-progress`: Task log opened, code or research happening.
- `blocked`: Waiting on dependency/decision. Include owner + ETA in notes.
- `ready-for-review`: Work complete, awaiting validation or approval.
- `completed`: Acceptance criteria met, code merged, documentation updated.

---

## 7. Daily Update Ritual

1. Spend 2 minutes updating this file before or after stand-up.  
2. Ensure `Implementation.md` mirrors the same task statuses for the current stage.  
3. Call out blockers in the dashboard table and tag the responsible owner.  
4. When a task finishes, copy the highlights into `.acontext/tasks/<log>.md` and mark the history location here.

Keeping Active_Tasks precise ensures every future contributor can see **what is ready, what is running, and where to look for context** without digging through chat logs or code diffs. Maintain it rigorously, and Implementation stays clean, Product_Backlog stays strategic, and .acontext stays actionable. 
