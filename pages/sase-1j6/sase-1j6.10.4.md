# Bead: sase-1j6.10.4 — Runner refresh imports, lifecycle facts, config, UX polish, and epic-caused test failures

[Bead Pages](../README.md) / [sase-1j6.10](sase-1j6.10.md) / sase-1j6.10.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1j6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.land.md) · **Assignee:** `sase-1j6.10.4` · **Size:** medium
**Created:** 2026-10-10 08:09:08 EDT · **Closed:** 2026-10-10 08:33:23 EDT
**Plan:** [202610/finish\_update\_skew\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md)

## Description

runner-ux-fixes: remove the remaining late imports before os.execv, fix lifecycle-phase and failure-facts capture gaps, move spare_process_patterns back under agent_scope_teardown, use UPDATE_RECOVERY_GLYPH everywhere, and fix the epic-caused completion, parser, schema, vocabulary, wire, timezone, lock-path, and import-budget test failures.

## Notes

[2026-10-10T12:33:09Z · sase-1j6.10.4] PROPOSED FOLLOW-UP: Reconcile the closed agents_unified_query definition (just check fails rule 7 on both this worktree and clean base; tracked by closed flag bead sase-zg and prior removal phase sase-1jc.6).

[2026-10-10T12:33:23Z · sase-1j6.10.4] Verified 140 targeted regression tests, the focused finalizer lifecycle test, and 2 TUI screenshot tests; screenshots needed no updates. Synced the CLI completion snapshot. just check stops at the closed agents_unified_query feature-flag rule, reproduced identically on clean base and recorded as a proposed follow-up. Epic-symbol audit found no leftovers.

## Dependencies

- **Blocks:** [sase-1j6.10.7](sase-1j6.10.7.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.10.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.4/README.md) | [sase-1j6.10.4](sase-1j6.10.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1728f2b`](https://github.com/sase-org/sase/commit/1728f2bcd0adcc957efc30111e69dcd50a791b32) | fix(runner): finish refresh lifecycle and recovery UX | [sase-1j6.10.4](sase-1j6.10.4.md) | 2026-10-10 08:35:04 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.10.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.4/README.md

<!-- sase:referenced-by:end -->
