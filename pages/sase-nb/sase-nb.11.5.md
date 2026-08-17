# Bead: sase-nb.11.5 — Report the bead id sase flag new actually committed

[Bead Pages](../README.md) / [sase-nb.11](sase-nb.11.md) / sase-nb.11.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-nb.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-nb.land.md) · **Assignee:** `sase-nb.11.5` · **Size:** small
**Created:** 2026-08-16 21:04:27 EDT · **Closed:** 2026-08-16 21:31:43 EDT
**Plan:** [202608/feature\_flags\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags_landing.md)

## Description

cli: read the flag bead's id back after the store mutation commits so the scaffold, the printed line, and the commit message all name the committed bead.

## Notes

[2026-08-17T01:31:05Z · sase-nb.11.5] COMMIT MESSAGE ORDERING: remint happens on the store commit/push conflict path after mutation.commit() freezes the message. bead_store_mutation itself does not remint. rust create allocates from next_counter (skipping local ids); auto_commit + push can then relocate a colliding id, as with sase-nv (pre-existing task bead) vs the committed flag bead sase-nw. The commit message therefore names the pre-remint allocation; the printed line and scaffold bead= are re-read by key after the mutation and name the committed id.

[2026-08-17T01:31:20Z · sase-nb.11.5] PROPOSED FOLLOW-UP: just check failed on init memory --check — home memory README drift at ~/.local/share/chezmoi/home/sase/memory/README.md (+3 −2). Unrelated to this phase (only beads.py + test_cli.py changed). Likely sase-nb.11.1 memory-init fallout or pre-existing chezmoi drift.

[2026-08-17T01:31:43Z · sase-nb.11.5] create_flag_bead re-reads the flag bead by key after bead_store_mutation returns (after commit/push remint). Forced stale-id test: printed line, scaffold bead=, and returned Issue all name the committed id; missing re-read raises FeatureFlagError. just check: fmt/ruff/mypy/flags/symvision green; validate failed on unrelated home memory README drift; just test-scoped 1025 passed. Commit message cannot name the reminted id (frozen before remint).

[2026-08-17T01:33:45Z · sase-nb.11.5] create_flag_bead re-reads the flag bead by key after bead_store_mutation returns (after commit/push remint). Forced stale-id test: printed line, scaffold bead=, and returned Issue all name the committed id; missing re-read raises FeatureFlagError. just check: fmt/ruff/mypy/flags/symvision green; validate failed on unrelated home memory README drift; just test-scoped 1025 passed. Commit message cannot name the reminted id (frozen before remint).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.11.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-nb.11.5/README.md) | [sase-nb.11.5](sase-nb.11.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d5443be`](https://github.com/sase-org/sase/commit/d5443be389eb33a105ad03c1372362c15a472ab9) | fix(flags): report the committed flag-bead id after remint | [sase-nb.11.5](sase-nb.11.5.md) | 2026-08-16 21:34:31 EDT |
