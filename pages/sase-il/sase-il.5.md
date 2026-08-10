# Bead: sase-il.5 — Retire the coder alias bucket

[Bead Pages](../README.md) / [sase-il](README.md) / sase-il.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wt](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wt/README.md) · **Assignee:** `sase-il.5` · **Size:** large
**Created:** 2026-08-09 16:44:34 EDT · **Closed:** 2026-08-10 10:32:00 EDT
**Plan:** [202608/sase\_sizes\_memory.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_sizes_memory.md)

## Description

coder-alias: delete the `coder` and `<provider>_coder` implicit aliases and route coder follow-ups through the phase-worker alias for the tale plan's size.

## Notes

[2026-08-10T14:32:00Z · sase-il.5] Implementation complete for retire_coder_alias_bucket. Verified: just install completed; just fmt clean; focused model/tale-follow-up subset passed; broad focused alias/follow-up suite passed earlier (906 passed); targeted visual snapshot set passed serial after intentional updates (34 passed); git diff --check clean. Final just check-full passed all lint/SASE/committed-plan gates, then failed only tracked unrelated test issues: contract manifest/budget (filed as sase-iv), run_pytest cost-mode health recorder expectations (sase-iq), ACE/TUI full-lane flakes recorded on sase-ct, and a recurring tasks-pane-store node reopened on sase-ii.

[2026-08-10T14:33:32Z · sase-il.5] Implemented retire_coder_alias_bucket; verified with just install, just fmt, git diff --check, focused alias/follow-up tests, targeted regression subset, targeted visual subset, and final just check-full attempt. Final full gate reached unrelated tracked failures: sase-iv, sase-iq, sase-ct, and sase-ii.

## Dependencies

- **Depends on:** [sase-il.4](sase-il.4.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-il.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-il.5.md) | [sase-il.5](sase-il.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`344a0b8`](https://github.com/sase-org/sase/commit/344a0b8ff2da71bc53123f008fde5ab08c1bef3a) | feat!: retire implicit coder model aliases | [sase-il.5](sase-il.5.md) | 2026-08-10 10:35:10 EDT |
