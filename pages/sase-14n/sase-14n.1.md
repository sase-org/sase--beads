# Bead: sase-14n.1 — Clear the 26 unused public symbols that abort every lint run

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.1` · **Size:** medium
**Created:** 2026-09-20 17:14:07 EDT · **Closed:** 2026-09-20 17:45:04 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

symvision: privatize, wire up, or delete the 26 unused public symbols reported by `just _lint-symvision` so `just check` reaches its later stages for every other phase.

## Notes

[2026-09-20T21:45:04Z · sase-14n.1] Privatized all 26 unused public symbols (_-prefix, in-file callers updated) across _store_clone_admission, _store_clone_remote, _agent_runner_slot_capacity, host_support, host_reporting, runtime_cache_generation; updated 9 test patch targets to private names; no pragmas or Justfile whitelist entries added; just _lint-symvision clean; recorded just check: symvision stage passes, 3240 passed with the single failure being the latch-phase test that also fails on the stashed clean tree (pre-existing, owned by another phase); sase-13s evidence carried in phase work

## Dependencies

- **Blocks:** [sase-14n.10](sase-14n.10.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.11](sase-14n.11.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.12](sase-14n.12.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.13](sase-14n.13.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.14](sase-14n.14.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.7](sase-14n.7.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.8](sase-14n.8.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.9](sase-14n.9.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.1/README.md) | [sase-14n.1](sase-14n.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`47e281b`](https://github.com/sase-org/sase/commit/47e281b7a0a60c029284dd9d7ac9d2b69661800b) | fix(lint): privatize 26 unused public symbols flagged by symvision | [sase-14n.1](sase-14n.1.md) | 2026-09-20 17:47:07 EDT |
