# Product Backlog (Developer-Friendly)

> Single place to park approved-but-not-scheduled work. Keep it short, keep IDs first, and make promotion to `Active_Task.md` obvious.

---

## 1) How This Folder Fits
- `project_management/` is the source of truth. `.acontext` and agents mirror it.
- Flow: `PRD` -> `Product_Backlog` (this file) -> `Active_Task` -> `.acontext/tasks` -> Code.
- Items here are manually synced with Notion; no auto-sync expected.

---

## 2) Backlog Snapshot (one-liners)

| ID | Title | Epic | Status | Priority | Ready? | Notion |
|----|-------|------|--------|----------|--------|--------|
| `PB-001` | `<Short outcome>` | `<Epic/Stage>` | idea/groomed/ready | H/M/L | Yes/No | `<Notion link or ID>` |

Use the table for quick scanning; details live in the entries below.

---

## 3) Lean Entry Template (YAML)

```yaml
- id: PB-001              # Required, keep stable for Git + Notion mapping
  title: "Outcome-based title"
  epic: "PRD epic or stage"
  status: idea | groomed | ready
  priority: high | med | low
  notion: "Notion task URL or ID"
  summary: >
    1-2 sentences on user value; what success looks like.
  acceptance_hints:
    - "Testable condition #1"
  dependencies:
    tech: []    # Keep short; list only blocking deps
    design: []  # Link to spec if needed
  notes: >
    Links to research/decisions. Keep brief.
```

Remove unused fields (`compliance`, RICE scores, t-shirt sizing). Keep this as the only schema.

---

## 4) Status Model (keep it simple)
- `idea`: captured but not vetted.
- `groomed`: scoped and understood; acceptance hints drafted.
- `ready`: meets Definition of Ready and can move to `Active_Task.md`.

---

## 5) Definition of Ready (developer-focused)
- Acceptance hints are testable.
- Blocking dependencies are known/owned.
- Design link present if UI work is involved.

If any box is unchecked, keep status below `ready`.

---

## 6) Promotion Rule
- When `status = ready`: move the item into `Active_Task.md`, open a `.acontext/tasks` log when work starts, and mark it as promoted here (optional note in `notes`).

---

## 7) Parking Lot (unvetted ideas)

```
- id: IDEA-001
  title: "What if..."
  notion: "<link or ID>"
  next_step: "Discovery interview / Prototype"
```

Move items into the main backlog template once they are real candidates.

---

## Usage Checklist
- [ ] Every entry has `id` + `notion` for traceability.
- [ ] Status sticks to `idea/groomed/ready` only.
- [ ] Table mirrors the entries below.
- [ ] Move `ready` items to `Active_Task.md` before coding starts.
