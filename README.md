# Napkin

Napkin is an explicitly invoked agent skill for capturing recurring repository lessons. It does not run at session start, read or rewrite notes during ordinary work, or create files during read-only tasks.

## Install

**Codex**

```bash
git clone https://github.com/blader/napkin.git ~/.agents/skills/napkin
```

**Claude Code**

```bash
git clone https://github.com/blader/napkin.git ~/.claude/skills/napkin
```

Restart the client after installation if the skill does not appear.

## Use

Invoke the skill when a correction or confirmed approach should survive beyond the current task.

**Codex**

```text
$napkin Capture this recurring lesson: run bin/ci before opening a PR.
```

**Claude Code**

```text
/napkin Capture this recurring lesson: run bin/ci before opening a PR.
```

Napkin first checks for an existing durable home:

- Required agent behavior goes in the closest applicable `AGENTS.md`.
- Explanatory operational guidance goes in an established repository runbook.
- Otherwise, one focused lesson is stored in `.agents/napkin/<short-slug>.md`.

Existing `.claude/napkin.md`, `.codex/napkin.md`, or `.Codex/napkin.md` files are migrated only when explicitly requested.

## Design boundaries

- Explicit invocation only; implicit activation is disabled in `agents/openai.yaml` for Codex and `SKILL.md` frontmatter for Claude Code.
- Store recurring, evidence-backed lessons, not session logs.
- Update duplicates and delete lessons that prove wrong.
- Never store secrets or transient task status.

## License

MIT
