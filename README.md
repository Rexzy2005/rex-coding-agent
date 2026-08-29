# DevRex Skills

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

AI agents are powerful. They're also stateless, pattern-matching tools that will confidently build the wrong thing if you let them.

Rex Skills give your AI agent the engineering discipline it doesn't have by default — memory between sessions, architectural thinking before you write a line, and structured review after. Five slash commands that keep you in the driver's seat.

They work with any agent that supports the SKILL.md format: Grok, Claude Code, Cursor, Windsurf, Codex, Cline, and more.

**Philosophy:** The problem isn't that AI writes bad code. It's that developers stop thinking when it writes fast code. These skills keep you thinking.

---

## Install

### Grok

Add this repo as a marketplace, then install the plugin:

```bash
grok plugin marketplace add Rexzy2005/rex-coding-agent
grok plugin install rex-skills --trust
```

Or install the plugin directly (no marketplace step):

```bash
grok plugin install Rexzy2005/rex-coding-agent --trust
```

From a local clone:

```bash
grok plugin install . --trust
```

After install, invoke the skills with these commands (verified against a live Grok session):

| Skill | Command that actually runs this plugin |
|---|---|
| architect | `/architect` |
| imprint | `/imprint` |
| recover | `/recover` |
| remember | `/rex-skills:remember` |
| review | `/rex-skills:review` |

`/architect`, `/imprint`, and `/recover` work as bare names. `/remember` and `/review` collide with Grok built-ins, so the bare names do **not** run this plugin — use `/rex-skills:remember` and `/rex-skills:review`. The qualified form `/rex-skills:<name>` also works for all five.

If the plugin is listed but inactive, run `grok plugin enable rex-skills` or press `Space` on it in `/plugins`.

### Other agents

```bash
npx skills@latest add Rexzy2005/rex-coding-agent
```

---

## Skills

### `/architect`

**Use before building anything.**

Think through what you are about to build like a senior engineer before writing any code. Surfaces decisions, aligns on language, and produces a clear implementation plan you confirm before anything starts.

This is not a grilling session. It is a thinking session — collaborative, not adversarial.

---

### `/rex-skills:remember`

**Use at the end and start of every session.**

AI has no memory between sessions. Every new session starts blank. This skill fixes that.

- `/rex-skills:remember save` — at end of session, compress what matters into memory.md
- `/rex-skills:remember restore` — at start of new session, restore full context and confirm before continuing

---

### `/rex-skills:review`

**Use after building any feature.**

Verify what was built is correct — not just that it works. Reviews in three layers: plan alignment, system integrity, and production readiness. Reports issues clearly so the developer decides what to fix.

Working and correct are not the same thing.

---

### `/recover`

**Use when something goes wrong.**

Not every problem is a bug. Not every bug needs debugging. This skill diagnoses which type of failure you are dealing with before deciding how to respond:

- **Targeted fix** — isolated problem, find root cause, fix precisely
- **Hard reset** — polluted session, stop patching, start fresh
- **Rethink** — wrong foundation, no amount of debugging helps

---

### `/imprint`

**Use after building any UI component.**

Extract the visual patterns that matter for consistency and save them to ui-registry.md. So every component built after this one matches what came before.

- `/imprint` — capture from recently built component
- `/imprint [file]` — capture from specific file
- `/imprint audit` — scan entire codebase, find conflicts, establish baseline

---

## The Engineering Loop

```
/architect  →  Build  →  /rex-skills:review  →  Ship
                 ↓
/imprint  (after every UI component)
/rex-skills:remember  (end and start of every session)
/recover   (when something breaks)
```

---

## Learn More

Built by [DevRex](https://github.com/Rexzy2005) — development education for serious engineers.

---

## Contributing

Found a bug or want to improve a skill? Open an issue or PR. Skills are just markdown — contributions are welcome from anyone.

---

## License

[MIT](LICENSE)
