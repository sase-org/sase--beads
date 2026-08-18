# Bead: sase-q0.5.1 — Atomic, checked workspace acquisition in the sase-github plugin

[Bead Pages](../README.md) / [sase-q0.5](sase-q0.5.md) / sase-q0.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-q0.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-q0.land.md) · **Assignee:** `sase-q0.5.1` · **Size:** medium
**Created:** 2026-08-18 17:40:17 EDT · **Closed:** 2026-08-18 18:01:18 EDT
**Plan:** [202608/gh\_plugin\_workspace\_exclusivity.md](https://github.com/sase-org/sase--plans/blob/main/202608/gh_plugin_workspace_exclusivity.md)

## Description

gh_atomic: replace the check-then-claim allocation in gh__setup and in the GitHub submit path with a single atomic claim, check every claim result, make a pinned n=<num> target a single-shot claim that names the occupant on failure, release the slot when materialization fails, and give every claim and release a caller tag.

## Notes

[2026-08-18T22:01:01Z · sase-q0.5.1] PROPOSED FOLLOW-UP: sase just check fails on pre-existing toobig — tests/_suite_gate.py is 1197 lines on current master (limit 1000); unrelated to the sase-github claim rewrite and not caused by this phase.

[2026-08-18T22:01:18Z · sase-q0.5.1] Atomic, checked claims in sase-github: gh__setup unpinned path uses claim_next_axe_workspace then ensure_workspace_checkout/materialize_sdd_store (releases the slot if either raises); pinned n=<num> is a single-shot claim_workspace that names the live occupant and exits 1 without materializing; claim results are never discarded; pre_allocated still skips claiming; ws_submit uses claim_next_axe_workspace_dir + finally release; caller tags are gh-setup / gh-submit / gh-release. Verified: sase-github just check 211 passed (atomic skip, release-on-fail, pinned occupant, submit finally, ledger tags); sase plugin consumer tests 34 passed; setup_required_plugins installs the local checkout; occupancy_conflicts doctor OK; no --epic-symbol leftovers. sase just check itself failed on pre-existing toobig (tests/_suite_gate.py).

[2026-08-18T22:03:07Z · sase-q0.5.1] Atomic, checked claims in sase-github: gh__setup unpinned path uses claim_next_axe_workspace then ensure_workspace_checkout/materialize_sdd_store (releases the slot if either raises); pinned n=<num> is a single-shot claim_workspace that names the live occupant and exits 1 without materializing; claim results are never discarded; pre_allocated still skips claiming; ws_submit uses claim_next_axe_workspace_dir + finally release; caller tags are gh-setup / gh-submit / gh-release. Verified: sase-github just check 211 passed (atomic skip, release-on-fail, pinned occupant, submit finally, ledger tags); sase plugin consumer tests 34 passed; setup_required_plugins installs the local checkout; occupancy_conflicts doctor OK; no --epic-symbol leftovers. sase just check itself failed on pre-existing toobig (tests/_suite_gate.py).

## Dependencies

- **Blocks:** [sase-q0.5.2](sase-q0.5.2.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-q0.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-q0.5.1/README.md) | [sase-q0.5.1](sase-q0.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-github | [`sase-github@61dd36f`](https://github.com/sase-org/sase-github/commit/61dd36fa1aef7ec71475608e19de3ddf91b67b74) | feat: claim GitHub workspaces atomically | [sase-q0.5.1](sase-q0.5.1.md) | 2026-08-18 18:03:55 EDT |
