# Bead: sase-en.1 — Stop re-probing git remotes and re-merging config in repo inventory

[Bead Pages](../README.md) / [sase-en](README.md) / sase-en.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sl.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sl.f1/README.md) · **Assignee:** `sase-en.1` · **Size:** medium
**Created:** 2026-08-03 08:39:53 EDT · **Closed:** 2026-08-03 09:26:08 EDT
**Plan:** [202608/bead\_show\_speed.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_show_speed.md)

## Description

inventory: memoize the per-primary git-origin probe and the sidecar identity/config derivation that collect_repo_inventory recomputes hundreds of times per command, with an explicit reset hook for the long-lived ACE TUI, and guard it with a subprocess-count regression test.

## Notes

[2026-08-03T13:24:52Z · sase-en.1] PROPOSED FOLLOW-UP: Investigate Agent CLI plugin PNG golden mismatches — isolated visual runs consistently render new Update history panels absent from config_center_agent_clis_marked_120x40 and config_center_agent_clis_update_preview_120x40 (0.670357% and 0.281415% changed pixels); the three retry/contention failures from the same saturated full-suite run passed in isolation.

[2026-08-03T13:26:08Z · sase-en.1] Verified 59 scoped tests pass; formatting, Ruff, mypy, Symvision, SASE validation, and committed-plan checks pass; live plain output for sase-bv and ref-bearing sase-cl is byte-identical; the workspace build performs 2 successful origin probes and benchmarks at 1.064 s / 2.113 s means versus 1.841 s / 3.184 s baselines. Full suite reached 25,707 passes; three saturation failures passed in isolation and two unrelated Agent CLI PNG mismatches were recorded as a PROPOSED FOLLOW-UP.

[2026-08-03T13:27:48Z · sase-en.1] Verified 59 scoped tests, byte-identical CLI output, origin-probe budget, cache invalidation, loaded-host benchmarks, and full lint/type/Symvision checks; unrelated PNG mismatches were recorded as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-en.4](sase-en.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-en.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-en.1/README.md) | [sase-en.1](sase-en.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`25e706f`](https://github.com/sase-org/sase/commit/25e706f76b593d8e3147c86fdd01cd3d457ae4b0) | perf(repo): cache inventory identity derivations | [sase-en.1](sase-en.1.md) | 2026-08-03 09:28:46 EDT |
