# Napkin

A skill for Claude Code that gives the agent persistent memory of its mistakes.

The agent maintains a markdown file in your repo (`.claude/napkin.md`) where it tracks what went wrong, what you corrected, and what worked. It reads the file at session start and writes to it continuously as it works. By session 3-5 the behavior shift is significant — the agent stops making mistakes you've already corrected and starts pre-empting issues before you catch them.

Baby continual learning in a markdown file.

## Install

**Claude Code**

```bash
git clone https://github.com/blader/napkin.git ~/.claude/skills/napkin
```

**Codex**

```bash
git clone https://github.com/blader/napkin.git ~/.codex/skills/napkin
```

That's it. The skill activates every session, unconditionally.

## How it works

1. **Session start**: Agent reads `.claude/napkin.md` in the current repo. If it doesn't exist, it creates one.
2. **During work**: Agent logs mistakes (its own and yours), corrections, patterns, preferences — as they happen, not just at session end.
3. **Over sessions**: The napkin compounds. Session 1 is normal. Session 3 the agent is catching things before you do. Session 5 it's a different tool.

## What gets logged

- Agent's own mistakes — wrong assumptions, bad approaches, failed commands
- Your corrections — anything you told it to do differently
- Tool/environment surprises — things about the repo that weren't obvious
- Your preferences — how you like things done
- What worked — successful approaches worth repeating

## The napkin

Lives at `.claude/napkin.md` in each repo. One per repo. The agent designs the initial structure and adapts it to the project's domain.

You can `.gitignore` it or commit it — your call. Committing it means other contributors' agents benefit from the same learned patterns. Ignoring it keeps it personal.

## License

MIT
