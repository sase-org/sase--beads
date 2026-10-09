# Bead: sase-1j6.4 — Skew witnesses and the read-only scan command

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.4` · **Size:** medium
**Created:** 2026-10-09 15:02:06 EDT · **Closed:** 2026-10-09 18:41:00 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

witness-scan: collect managed roots and the W1-W3 witnesses (boot identity drift, update journal, file-level proof with the culprit commit), build legacy inputs from logs, and ship `sase agent auto-restart scan` for corpus replay.

## Notes

[2026-10-09T22:29:24Z · sase-1j6.4] scan -s 120d (workspace build, host corpus ~/.sase): 821 failures classified, 0 errors. Modes: 0 relaunch, 1 defer, 22 notify_post_provider, 0 ask, 798 decline. The defer is 0yz, the surviving 2026-10-09 incident row (Tier1 cannot_import_name auto_launch_prefix, pre_provider, W2+W3, probe_pending): historical pre-provider skew classifies defer as required. Zero relaunch among non-skew failures. The 22 notify rows are post-provider skew signatures with provider frames (held workspaces, correctly not relaunched). Witnessless skew-shaped rows (Sep 18 AGENT_HOLDS_FLAG ImportError, Sep 25 wire-schema ValueErrors) correctly decline with no_update_witness: no journal row and no boot snapshot on those legacy rows.

[2026-10-09T22:29:30Z · sase-1j6.4] PROPOSED FOLLOW-UP: decisions-web record for update-skew auto-restart design (at most once per lineage, pre-provider only); skipped per epic auto-decision decision_record=no

[2026-10-09T22:29:35Z · sase-1j6.4] PROPOSED FOLLOW-UP: symvision unused-public leftovers from sase-1j6.3 await healer consumers (facade claim/advance/lineage/episode/in-flight/schema fns; AgentFailure ChainLink/Frame/ImportError/AttributeError, LedgerHistory, Probe wires); proven pre-existing on clean base via worktree. Healer phase sase-1j6.5 should consume them or add --epic-symbol rows re-keyed to itself. Deleted only the dead private _opt_int helper in the same file.

[2026-10-09T22:41:00Z · sase-1j6.4] Closed by explicit `sase stitch create -B close` after create_commit landed 3ba224b9c1 ("feat(agent): skew witnesses and read-only auto-restart scan"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1j6.4` if more work remains.

## Dependencies

- **Depends on:** [sase-1j6.3](sase-1j6.3.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.5](sase-1j6.5.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.4/README.md) | [sase-1j6.4](sase-1j6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3ba224b`](https://github.com/sase-org/sase/commit/3ba224b9c1875fc3b8f60a4ebae9efc922917980) | feat(agent): skew witnesses and read-only auto-restart scan | [sase-1j6.4](sase-1j6.4.md) | 2026-10-09 18:36:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.4/README.md

<!-- sase:referenced-by:end -->
