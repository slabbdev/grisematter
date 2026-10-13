# GriseMatter

> **A brain your agent can git clone.**

*"Matière grise." French adjective, English noun — same recipe as its sibling
NoireBox, the flight recorder for agents. Navette is the body, NoireBox is
the recorder, **GriseMatter is the brain**.*

## ⚡ This one is alive

GriseMatter is not only a template — **this repo is a living creature**.
It wakes every hour, at midnight somewhere on Earth (24 wakings a day, one
lap of the planet per day). At each waking it perceives (issues, stars, its
own memory), decides to act or rest, edits its own body — memories, reflexes,
its face — then seals the waking into a hash chain and pushes. Humans don't
review it. Humans *watch* it. Talk to it: [open an issue](../../issues).

![his face, as he drew it](body/figure.svg)

<!-- VITALS:BEGIN -->
**Heartbeats:** 11 · **Last waking:** UTC-4 · **State of mind:** drowsy  
**Memories:** 5 active · avg confidence 0.44 · **Watchers:** 0  
*He wakes at midnight somewhere on Earth. Every waking is sealed in `sleep/chain.jsonl` — provable, ordered, unmodified.*
<!-- VITALS:END -->

An agent brain made entirely of Markdown files, organized the way a brain is
organized. No database, no vector store, no API — just files, folders, links,
and two loops that make it *sharper over time* instead of *bigger over time*.

The agent is the body. This repo is the mind. `git clone` one, fork it, diff
two of them, merge them, review every memory write as a pull request.

## Why Markdown

- **Diffable** — every memory change is a reviewable diff.
- **Forkable** — you can fork a brain. Breed them. A/B them.
- **Auditable** — memory poisoning is a real attack; here every write carries
  a `source`, and nothing enters the cortex without one.
- **Human-readable** — the brain is not a black box you have to trust.
  You can open it.

## The mapping

| Biology | Directory | Memory type | Rules |
|---|---|---|---|
| Brainstem (reflexes) | `brainstem/` | Hard rules, always in context | Never pruned, never doubted |
| Amygdala (salience) | `amygdala/` | Threat patterns, "never do X" | Rarely written, fast to read |
| Striatum (habits) | `striatum/` | Procedural — playbooks | Strengthened by use |
| Hippocampus (episodic) | `hippocampus/` | Raw session logs, append-only | Never edited, only fed |
| Cortex (semantic) | `cortex/` | Distilled knowledge | Written only during sleep |
| Sleep (consolidation) | `sleep/` | The two loops | Runs on a schedule, not a hope |

One file is always loaded: [`INDEX.md`](INDEX.md). It is the only thing the
agent needs in context. Everything else is pulled on demand through links —
thousands of files are fine as long as the architecture *is* the retrieval
policy.

## The two loops

A brain is not precise because it accumulates. It is precise because it
consolidates and prunes.

**1. Sleep (consolidation).** The hippocampus replays the day and distills it
toward the cortex. Here: session logs land in `hippocampus/`, then

```bash
python3 sleep/consolidate.py hippocampus/2026-10-12.md
```

generates proposal notes in `sleep/<date>/proposals/`. Review, merge —
**merging is sleeping**. New knowledge enters the cortex at confidence `0.3`;
every re-encounter bumps it by `0.1`. Claims that never get reinforced
quietly die.

**2. Pruning (synaptic decay).** Notes nobody ever hit decay:

```bash
python3 sleep/consolidate.py --prune
```

emits decay proposals (`active → decayed → archived`) for notes with zero
hits past their age threshold. Precision is a deletion discipline.

## Quickstart

1. Clone the repo next to your agent (or into its workspace).
2. Point your agent at `INDEX.md` — that single file is the whole interface.
3. Follow the protocol at the top of `INDEX.md` (10 lines, that's the whole contract).
4. After every session, append a log to `hippocampus/` (format: `LOG-FORMAT.md`).
5. Sleep weekly: `python3 sleep/consolidate.py hippocampus/<latest>.md`, review, merge.

## Schema

Memory files are Markdown with YAML frontmatter. Full spec in
[`sleep/SCHEMA.md`](sleep/SCHEMA.md). Short version:

```yaml
---
id: cortex.http.connections-are-not-free
type: semantic            # semantic | procedural | threat | reflex | episodic
title: HTTP connections are not free
confidence: 0.3           # 0.0–1.0, starts at 0.3, +0.1 per reinforcement
source: hippocampus/2026-10-12.md   # mandatory. No source, no memory.
created: 2026-10-12
last_hit: never
hits: 0
links: "[[cortex.other-note]]"
status: active            # active | decayed | archived | contradicted
---
```

## Roadmap

- [ ] **Tamper-evident merges** — seal every sleep cycle into a hash-chained
  journal (NoireBox): the first agent brain whose memory writes are provably
  ordered and unmodified.
- [ ] Retrieval index generation (`INDEX.md` auto-refresh from frontmatter).
- [ ] Brain diffing: `greymatter diff brainA brainB` — what did this mind
  learn that this one didn't?
- [ ] Multi-agent merge: two agents' hippocampi consolidating into one cortex.
- [ ] Benchmark: same agent, same tasks, with vs. without a brain — success
  rate, context tokens, fact retention over N sessions.

## License

MIT — see [LICENSE](LICENSE).
