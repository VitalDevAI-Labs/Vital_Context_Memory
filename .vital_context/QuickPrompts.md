## Universal Prompt

Use this to start **any** task with an AI agent:

```
Read .vital_context/CONTEXT.md.
Task: [describe the work].

1. Create .vital_context/tasks/task-YYYYMMDD-NNN-[name].md with goal + plan.
2. Check referenced docs ONLY if CONTEXT.md points you there for this type of work.
3. Implement. Log key steps and decisions in the task file.
4. Update the Active Tasks table in CONTEXT.md and tasks/index.md when done.
```

### Variants

**Bug fix:**
```
Read .vital_context/CONTEXT.md. Check .vital_context/bugs.md.
Bug: [describe the bug].
Fix it, log in .vital_context/tasks/, update bugs.md with resolution.
```

**Resume previous work:**
```
Read .vital_context/CONTEXT.md. Read .vital_context/tasks/task-YYYYMMDD-NNN-[name].md.
Continue from where it left off. Update the task log when done.
```

**Agentic auto-dev (minimal intervention):**
```
Read .vital_context/CONTEXT.md. Pick the next active task from the Active Tasks table.
Execute it end-to-end following the universal prompt workflow.
When done, pick the next task. Continue until all active tasks are complete.
```
