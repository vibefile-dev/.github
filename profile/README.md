# vibefile.dev

> The Makefile for the AI & vibe coding era.

A Makefile encodes **how**. A Vibefile only encodes **what** and **when** — the AI figures out the how by reading your repo.

```makefile
# Vibefile

seed: build
    "populate the database with realistic fake data for 10 users"

ship: test build
    "run tests, build, and deploy to production on fly.io"
    @require clean tests

test:
    "run the full test suite and surface any failures"

build:
    "compile and bundle the project for production"
```

```sh
vibe run ship
```

Same dependency model as Make. Plain English recipes. The AI reads your repo context and generates the correct commands for your specific stack — then executes them with live output.

---

## Repos

| Repo | Description |
|------|-------------|
| [`website`](https://github.com/vibefile-dev/website) | vibefile.dev — the landing page |
| [`spec`](https://github.com/vibefile-dev/spec) | The Vibefile format specification (COMING SOON) |

---

## The idea

Makefiles have survived 50 years because the model is right: a named task, its dependencies, and a recipe. But the recipes go stale. You come back six months later and find 40 lines of bash with no hint of what it was supposed to do or whether it still works.

Vibe coding has made this worse. AI writes most of the implementation now — but the glue scripts holding everything together are still hand-crafted shell, still brittle, still unreadable.

Vibefile fixes the recipe, not the model. You declare intent in plain English. The CLI collects relevant repo context — file tree, configs, existing scripts — and asks an LLM to generate the right commands for your stack. The Vibefile becomes your project's runbook: readable by humans, executable by machines.

Three execution modes:

- **Codegen** — plain prompt → AI generates shell → executes. Stateless and fast.
- **Agent** — `@mcp` directive → AI gets real tool access to services like Fly.io, GitHub, Postgres. Can inspect state and recover from errors.
- **Skill** — `@skill` directive → use a published `SKILL.md` instead of writing a prompt yourself.

→ [Read the full idea](https://vibefile.dev/idea.html)

---

## Status

Early stage. The spec is being written. Come shape it.

- 💬 [Join the Discord](https://discord.gg/3TsMMvK8tV)
- 🌐 [vibefile.dev](https://vibefile.dev)
- 📄 [Read the spec](https://github.com/vibefile-dev/spec)
