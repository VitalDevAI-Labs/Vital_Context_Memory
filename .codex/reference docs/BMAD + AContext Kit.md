# Documentation Standard – BMAD + AContext Reference Kit

> Use this guide to keep every Markdown file in the template consistent, purpose-driven, and cross-linked. It distills the research notes into a concise checklist you can apply to any new project.

---

## 1. Universal Requirements

1. **Document Purpose** – Each Markdown file begins with a short statement describing why it exists.
2. **Document Meta Table** – Include fields such as Owner, Last Updated, Status, Linked Docs.
3. **How-To Section** – Explain when to read the file, what input it expects, and the outputs people should produce.
4. **Cross-References** – Link to neighboring docs (PRD → Product_Backlog → Active_Task → Implementation → .acontext).
5. **Project-Agnostic Examples** – Use placeholders or generic scenarios so the template can be dropped into any repository.

---

## 2. Flow of Work

```
PRD (product vision)
    ↓
Product_Backlog (approved future work)
    ↓
Active_Task (groomed current-stage tasks)
    ↓
Implementation (stage plan)
    ↓
.acontext/tasks (execution logs)
    ↓
Code & Tests
```

Every file in Docs/ should reinforce where it sits in this flow.

---

## 3. Required Files & Contents

| File | Purpose | Key Sections |
|------|---------|--------------|
| `PRD.md` | Capture product vision and epics. | Meta, Personas, Problem Statements, Goals, Epics, Scenarios, Risks. |
| `Product_Backlog.md` | Store future features not in current MVP. | Purpose, Intake Flow, Feature Template, Prioritization, Ideas. |
| `Active_Task.md` | Groomed tasks ready for execution. | Dashboard, YAML task entries, Grooming checklist, Status definitions. |
| `Implementation.md` | Plan for current MVP stage. | Scope alignment, Stage blueprint, Stage playbooks, Quality plan, Risks. |
| `project_structure.md` | File, naming, and tooling conventions. | Directory tree, naming, imports, testing, branching rules. |
| `UI_UX_doc.md` | Design tokens + component specs. | Principles, tokens, components, interaction patterns, accessibility. |
| `Bug_tracking.md` | Defect log + playbook. | Status board, bug template, patterns, incident guide. |
| `.acontext/README.md` | Explain dynamic context system. | Directory map, capture rules, maintenance cadence. |
| `.acontext/AGENT_WORKFLOW.md` | Step-by-step instructions for agents. | Four-phase loop, task log lifecycle, prompts, checklist. |
| `.acontext/Developer Playbook.md` | End-to-end workflow + rituals. | Principles, lifecycle, review gates, troubleshooting. |
| `.acontext/QUICK_PROMPTS.md` | Copy/paste instructions for agents. | Standard feature, bug, research, resume, review prompts. |
| `.acontext/tasks/*` | Task index/template + example logs. | Template updated with generic sections; examples illustrate usage. |
| `meta_files/*` | Deep dives (e.g., storage, notification testing). | Purpose, stack overview, scenario checklists. |

---

## 4. Style Guidelines

- **Plain ASCII** – Avoid special characters unless necessary.
- **Consistent Headings** – Use `##` for major sections, `###` for subsections.
- **Tables over prose** when enumerating metadata or comparisons.
- **Code fences** for YAML/JSON or prompts.
- **Checklists** for readiness/validation steps.

---

## 5. Maintenance Cadence

| Cadence | Action |
|---------|--------|
| Sprint start | Refresh Active_Task + Implementation stage entries. |
| Sprint end | Archive completed task logs, update Bug_tracking patterns. |
| Monthly | Audit documentation meta tables for freshness. |
| Major release | Snapshot docs (tag or branch) and record change log. |

---

## 6. Review Checklist

- [ ] Each doc states its purpose and how to use it.
- [ ] Meta tables populated with current owner/date.
- [ ] Cross-links exist between PRD → Backlog → Active Tasks → Implementation → AContext.
- [ ] Examples use neutral wording (no product-specific details).
- [ ] Task logs reference Active_Task IDs and Implementation stages.
- [ ] Meta guides (storage, notifications) highlight how to adapt to different stacks.

---

## 7. Extending the Template

- When adding a new doc, clone an existing structure: purpose → meta → usage → templates → checklists.
- Record the addition in Implementation (Stage 0 or process stage) and `.acontext/decisions`.
- Share changes in `.acontext/Developer Playbook.md` so prompts and workflows stay aligned.

---

