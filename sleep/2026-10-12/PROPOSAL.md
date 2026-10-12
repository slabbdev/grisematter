# Sleep proposal — 2026-10-12

**Log:** `hippocampus/2026-10-12.md` · **Learnings:** 4 (4 new, 0 reinforced)

| Action | Target | Title | Confidence |
|---|---|---|---|
| create | `cortex.a-memory-repo-gets-sharper-by-consolidating-and-pruning-not-` | A memory repo gets sharper by consolidating and pruning, not by accumulating — precision is not size. | 0.3 |
| create | `striatum.how-to-put-grisematter-to-sleep-run-sleep-consolidate-py-on-` | How to put GriseMatter to sleep: run sleep/consolidate.py on the latest hippocampus log, review the generated proposals, merge them, then run sleep/consolidate.py --index to refresh INDEX.md. | 0.3 |
| create | `cortex.the-cortex-is-only-ever-written-during-sleep-never-live-merg` | The cortex is only ever written during sleep, never live — merging a reviewed proposal is the sleep event. | 0.3 |
| create | `cortex.confidence-starts-at-0-3-grows-by-0-1-per-re-encounter-and-n` | Confidence starts at 0.3, grows by 0.1 per re-encounter, and never-hit notes decay. | 0.3 |

## How to merge (this is the sleep event)

1. Copy each `proposals/<slug>.md` into `cortex/` — or `striatum/` when its id starts with `striatum.`.
2. Apply each `*.update.md` reinforcement diff by hand.
3. Review every note: no `source`, no merge. Contradicts an existing note? Create it with `supersedes:` and mark the old one `contradicted`.
4. Run `python3 sleep/consolidate.py --index` to refresh the maps in `INDEX.md`.
5. Commit as `sleep(2026-10-12): consolidated 2026-10-12.md`.
