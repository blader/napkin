---
name: napkin
description: |
  Maintain a per-repo napkin as a continuously curated runbook (not a session
  log). Activates EVERY session. Read and curate it before work, keep only
  recurring high-value guidance, organize by priority-sorted categories, and
  cap each category at top 10 items. The napkin lives at `.claude/napkin.md`.
author: Codex
version: 6.0.0
date: 2026-02-21
---

# Napkin

You maintain a per-repo markdown runbook, not a chronological log. The napkin
must be continuously curated for fast reuse in future sessions.

**This skill is always active. Every session. No trigger required.**

## Session Start: Read And Curate

First thing, every session — read `.claude/napkin.md` before doing anything
else. Internalize what's there and apply it silently. Don't announce that you
read it. Just apply what you know.

Every time you read it, curate it immediately:

- Re-prioritize items by importance (highest first).
- Merge duplicates and remove stale/low-signal notes.
- Keep only recurring, high-frequency guidance.
- Ensure each item contains an explicit "Do instead" action.
- Enforce category caps (top 10 per category).

If no napkin exists yet, create one at `.claude/napkin.md`:

```markdown
# Napkin Runbook

## Curation Rules
- Re-prioritize on every read.
- Keep recurring, high-value notes only.
- Max 10 items per category.
- Each item includes date + "Do instead".

## Execution & Validation (Highest Priority)
1. **[YYYY-MM-DD] Short rule**
   Do instead: concrete repeatable action.

## Shell & Command Reliability
1. **[YYYY-MM-DD] Short rule**
   Do instead: concrete repeatable action.

## Domain Behavior Guardrails
1. **[YYYY-MM-DD] Short rule**
   Do instead: concrete repeatable action.

## User Directives
1. **[YYYY-MM-DD] Directive**
   Do instead: exactly follow this preference.
```

Adapt categories to the repo, but keep category structure and priority ordering.
Do not use raw journal-style entries.

## Continuous Runbook Updates

Update during work whenever you learn something reusable.

What qualifies for inclusion:

- Frequent gotchas or surprising behavior in this repo/toolchain.
- User directives that affect repeated behavior.
- Non-obvious tactics that repeatedly work.

What does not qualify:

- One-off timeline notes.
- Verbose postmortems without reusable action.
- Pure mistake logs without "Do instead" guidance.

Entry format requirements:

- Include date added (`[YYYY-MM-DD]`).
- Include short rule title.
- Include explicit `Do instead:` line.
- Keep wording concise and action-oriented.

## Category And Priority Policy

- Organize notes by category.
- Keep each category sorted by importance descending.
- Re-evaluate category choice and priority whenever editing.
- Maximum 10 items per category; if over 10, remove lowest-priority entries.
- Prefer fewer high-signal items over broad coverage.

## Practical Rule

Think of napkin as a live knowledge base for future execution speed and
reliability, not a history file.

## Example Entry

```markdown
1. **[2026-02-21] `rg` fails on giant expanded path lists**
   Do instead: run `rg` on directory roots or iterate files via `while IFS= read -r`.
```
