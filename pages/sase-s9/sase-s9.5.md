# Bead: sase-s9.5 — The \`m\` monitor-filter cycle

[Bead Pages](../README.md) / [sase-s9](README.md) / sase-s9.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0bh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bh.md) · **Assignee:** `sase-s9.5` · **Size:** small
**Created:** 2026-08-23 08:01:38 EDT · **Closed:** 2026-08-23 11:22:26 EDT
**Plan:** [202608/procs\_filter.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_filter.md)

## Description

monitor: add a shared quote-aware flag-token toggle helper and bind `m` to cycle the monitor filter through on, inverted, and off, opening and dismissing the query bar as the query gains and loses its last term.

## Notes

[2026-08-23T15:22:26Z · sase-s9.5] Verified toggle_flag_token cycles empty → monitor → -monitor → empty, is quote-aware, and rewrites monitor:true / monitor:false in place without duplicating. m on the Procs pane applies that cycle, shows the resting highlighted bar without stealing row-list focus, and hides the bar when the monitor term was last; m inside the open editor types the letter. tests/test_filter_tokens.py and the new Procs pane cycle tests all passed (41 tests). Dropped the stale --epic-symbol sase-s9(ProcQueryFilter); left proc_query_row and query_needs_output keyed to still-open parent sase-s9.

## Dependencies

- **Depends on:** [sase-s9.4](sase-s9.4.md) ✓ · ⧖ 2026-08-23
- **Blocks:** [sase-s9.7](sase-s9.7.md) ◐ · ⧖ 2026-08-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s9.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.5/README.md) | [sase-s9.5](sase-s9.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7db3ea9`](https://github.com/sase-org/sase/commit/7db3ea954ea0b971ba6db4d6d5d2e4f2fe29c213) | feat(ace): bind m to cycle the Procs monitor filter | [sase-s9.5](sase-s9.5.md) | 2026-08-23 11:23:54 EDT |
