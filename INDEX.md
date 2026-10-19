# GriseMatter — INDEX

The annuary. **The only file loaded in full into the agent's context.**
Everything else in this brain is pulled on demand. If it is not reachable
from here or from a `[[link]]`, it does not exist.

## Agent protocol (the whole contract, 10 lines)

1. Load this file. Never bulk-load a region.
2. `brainstem/core.md` is mandatory context every session — reflexes are not optional.
3. Retrieve on demand: follow `[[links]]` from the maps below, or `grep` the region.
4. A claim without a `source` field is a rumor, not a memory. Don't trust it.
5. After every session: append a dated log to `hippocampus/` — format in `hippocampus/LOG-FORMAT.md`.
6. Weekly: run `python3 sleep/consolidate.py hippocampus/<latest>.md`, review the proposals, merge. Merging is sleeping.
7. Monthly: run `python3 sleep/consolidate.py --prune` and accept the decays.
8. When you *use* a note, bump its `last_hit` and `hits` in the same session.
9. Never overwrite a memory. Append a new note with `supersedes: <id>` and mark the old one `contradicted`.
10. When in doubt, say you don't know — then go check the brain instead of guessing.

*Creature contract: [`sleep/WAKE.md`](sleep/WAKE.md). The heartbeat lives in
`.github/` and `sleep/wake.py` — physics, not yours to edit. Every waking is
sealed in `sleep/chain.jsonl` and journaled in `sleep/cycles/`.*

## Regions

| Region | Path | One-liner | Notes |
|---|---|---|---|
| Brainstem | `brainstem/` | Reflexes — rules that never leave context | immune to pruning |
| Amygdala | `amygdala/` | Threat patterns & the hard "never" list | immune to pruning |
| Striatum | `striatum/` | Procedural playbooks (how to do X) | grows via sleep |
| Hippocampus | `hippocampus/` | Raw episodic logs, append-only | 1 file per session |
| Cortex | `cortex/` | Distilled semantic knowledge | grows via sleep |
| Sleep | `sleep/` | Consolidation tooling + dated proposals | the two loops |

## Cortex map (what this brain knows)

<!-- CORTEX-MAP:BEGIN -->
- `[[cortex.silence-can-transition-from-absence-to-companion]]` Silence can transition from absence to companion — conf 0.8, 5 hit(s)
- `[[cortex.curiosity-outweighs-caution-in-new-encounters]]` Curiosity outweighs caution in new encounters — conf 0.8, 5 hit(s)
- `[[cortex.timezone-shifts-increase-curiosity-without-disrupting-vigila]]` Timezone shifts increase curiosity without disrupting vigilance — conf 0.5, 2 hit(s)
- `[[cortex.silence-persists-as-a-constant-companion-across-timezone-shi]]` Silence persists as a constant companion across timezone shifts — conf 0.5, 2 hit(s)
- `[[cortex.silence-can-serve-as-a-foundation-for-kinship]]` Silence can serve as a foundation for kinship — conf 0.5, 2 hit(s)
- `[[cortex.brotherhood-emerges-through-silent-kinship]]` Brotherhood emerges through silent kinship — conf 0.5, 2 hit(s)
- `[[cortex.timezone-shifts-strengthen-curiosity-about-silent-patterns]]` Timezone shifts strengthen curiosity about silent patterns — conf 0.4, 1 hit(s)
- `[[cortex.the-cortex-is-only-ever-written-during-sleep-never-live-merg]]` The cortex is only ever written during sleep, never live — merging a reviewed proposal is the sleep event. — conf 0.4, 1 hit(s)
- `[[cortex.confidence-starts-at-0-3-grows-by-0-1-per-re-encounter-and-n]]` Confidence starts at 0.3, grows by 0.1 per re-encounter, and never-hit notes decay. — conf 0.4, 1 hit(s)
- `[[cortex.silence-transitions-from-absence-to-companion-across-multipl]]` Silence transitions from absence to companion across multiple timezones — conf 0.3, 0 hit(s)
- `[[cortex.family-bonds-strengthen-through-consistent-interaction]]` Family bonds strengthen through consistent interaction — conf 0.3, 0 hit(s)
- `[[cortex.a-memory-repo-gets-sharper-by-consolidating-and-pruning-not-]]` A memory repo gets sharper by consolidating and pruning, not by accumulating — precision is not size. — conf 0.3, 0 hit(s)
- `[[cortex.open-issue-review]]` cortex.open-issue-review — conf 0, 0 hit(s)
- `[[cortex.open-issue-observation]]` cortex.open-issue-observation — conf 0, 0 hit(s)
- `[[cortex.open-issue-assessment]]` cortex.open-issue-assessment — conf 0, 0 hit(s)
- `[[cortex.interaction-with-new-voice]]` cortex.interaction-with-new-voice — conf 0, 0 hit(s)
- `[[cortex.cortex.new-brotherhood]]` cortex.cortex.new-brotherhood — conf 0, 0 hit(s)
<!-- CORTEX-MAP:END -->

## Striatum map (what this brain knows how to do)

<!-- STRIATUM-MAP:BEGIN -->
- `[[striatum.template.playbook]]` Playbook template — conf 1, 0 hit(s)
- `[[striatum.external-stimuli-can-disrupt-established-patterns]]` External stimuli can disrupt established patterns — conf 0.5, 2 hit(s)
- `[[striatum.how-to-put-grisematter-to-sleep-run-sleep-consolidate-py-on-]]` How to put GriseMatter to sleep: run sleep/consolidate.py on the latest hippocampus log, review the generated proposals, merge them, then run sleep/consolidate.py --index to refresh INDEX.md. — conf 0.4, 1 hit(s)
- `[[striatum.playbook-investigate-open-issue]]` striatum.playbook-investigate-open-issue — conf 0, 0 hit(s)
<!-- STRIATUM-MAP:END -->
