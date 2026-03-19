## Universal Prompt

Use this to start **any** task with an AI agent:

```
Read docs/CONTEXT.md.
Task: [describe the work].

1. Create docs/tasks/task-YYYYMMDD-NNN-[name].md with goal + plan.
2. Check referenced docs ONLY if CONTEXT.md points you there for this type of work.
3. Implement. Log key steps and decisions in the task file.
4. Update the Active Tasks table in CONTEXT.md and tasks/index.md when done.
```

### Variants

**Bug fix:**
```
Read docs/CONTEXT.md. Check docs/bugs.md.
Bug: [describe the bug].
Fix it, log in tasks/, update bugs.md with resolution.
```

**Resume previous work:**
```
Read docs/CONTEXT.md. Read docs/tasks/task-YYYYMMDD-NNN-[name].md.
Continue from where it left off. Update the task log when done.
```

**Agentic auto-dev (minimal intervention):**
```
Read docs/CONTEXT.md. Pick the next active task from the Active Tasks table.
Execute it end-to-end following the universal prompt workflow.
When done, pick the next task. Continue until all active tasks are complete.
```
