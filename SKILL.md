---
name: napkin
description: Capture or curate a recurring repository lesson only when the user explicitly invokes $napkin or asks to record, update, or migrate durable repo memory. Do not use for session startup, routine work, one-off status, or read-only analysis.
disable-model-invocation: true
---

# Napkin

Capture durable repository lessons without turning ordinary tasks into a memory-maintenance workflow.

## Workflow

1. Confirm the lesson is recurring, non-obvious, and likely to change future work. Do not store transient status, one-off failures, secrets, or facts already clear from the repository.
2. Search the nearest applicable `AGENTS.md`, established runbooks, and existing lesson files for duplicates or contradictions.
3. Use the narrowest durable location:
   - Put required agent behavior in the closest applicable `AGENTS.md`.
   - Put explanatory operational guidance in an established repository runbook.
   - If neither exists and the user asked to capture the lesson, create `.agents/napkin/<short-slug>.md` with one lesson per file.
4. Update an existing lesson instead of creating a duplicate. Remove or supersede a lesson only when current evidence shows it is wrong.
5. Keep the change concise and report the exact destination.

## Lesson Format

For `.agents/napkin/<short-slug>.md`, use:

```markdown
# One-line lesson

Date: YYYY-MM-DD

Why it matters: Brief evidence or context.

Do instead: Concrete repeatable action.
```

## Migration

When explicitly asked to migrate an older `.claude/napkin.md`, `.codex/napkin.md`, or `.Codex/napkin.md`, evaluate each entry independently. Move mandatory rules to `AGENTS.md`, move useful operational context to an established runbook, and discard stale, duplicated, or one-off notes. Do not migrate automatically.
