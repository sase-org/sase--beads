# Bead: sase-1n6.11.1 — The steward reads a real merge gate from the N1 inventory

[Bead Pages](../README.md) / [sase-1n6.11](sase-1n6.11.md) / sase-1n6.11.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.land.md) · **Assignee:** `sase-1n6.11.1` · **Size:** medium
**Created:** 2026-11-03 09:51:13 EST · **Closed:** 2026-11-03 18:35:08 EST
**Plan:** [202611/e2\_steward\_train\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202611/e2_steward_train_completion.md)

## Previously Closed

> ↺ Closed 2026-11-03T15:54:39Z · done
>
> (none)
>
> Reopened 2026-11-03T21:46:30Z by `sase bead open`

## Description

merge-checks: the steward's expected release-PR checks come from the versioned N1 inventory instead of absent branch protection, and Master Gate is judged on its own jobs rather than on the PR's check list (sase-core plus sase).

## Notes

[2026-11-03T15:54:27Z · sase-1n6.11.1] Landed contract (merge-checks): inventory schema v2 (.github/release-qualification.json) with merge_gate required_checks ["Conventional PR title", "prepare", "release-core-floor-smoke"], inventory digest 09ead2c4e6f8fe4ebb62581eb28dd12113ac27c1cfe509e8cdb916a07f891c67; steward wire schema v2 (tools/_release_watch_decide.py, sase-core wire.rs, binding release_steward_wire_schema_version()=2); master facts carry expected_checks_source=release-qualification inventory plus inventory_digest; master_gate_green judges Master Gate on its own jobs (all success, SKIPPED/cancelled/missing red), pr_checks_green enforces the inventory PR list. sase-core HEAD base f1bbb4f3b81383c06df422c9df9fa13f0ec244f7, sase-core-revision.txt pin f1bbb4f3b81383c06df422c9df9fa13f0ec244f7 (pin ratchet past the new core commit follows host commit). Verification: sase-core sase tool run check e47fcfbce6cb456ddf1f984914248bd8 succeeded exit 0; sase targeted pytest 48 passed (merge_gate 2, decide 6 incl real v2 binding round-trip, inventory 38); live tools/release_watch --once --json exit 0 primary core_cut_red schema_version 2 (past merge-gate, not unreadable). Full sase just check 155d1572 was joined by staged monitor vrtdeh and still running at close; targeted + live evidence above is the merge-checks proof.

[2026-11-03T15:54:39Z · sase-1n6.11.1] merge-checks done: inventory v2 merge-gate [Conventional PR title, prepare, release-core-floor-smoke], wire v2, Master Gate judged on own jobs; sase-core check green, sase targeted 48 passed incl real v2 binding, live --once core_cut_red schema 2 exit 0 (past merge-gate, not unreadable). No epic-symbols. Pin ratchet past new core commit follows host commit.

[2026-11-03T21:44:52Z · sase-1n6.11.1] CLOSED-BEAD LAUNCH: agent sase-1n6.11.1 launched against this closed bead; status left closed.
Launch submitted 2026-11-03T21:43:37.918752Z; run 20261103164339.
Prior close: 2026-11-03T15:54:39Z · done.

[2026-11-03T21:46:35Z · sase-1n6.11.1] Recovery verification: fetched origin/master in both repos. Sase e7617d9827 still has inventory schema 1, Python wire 1 and branch-protection required checks; core bbef1df2 still has wire 1 and shared Master Gate/PR check list. No merge-checks commit in either history. Prior completion notes describe work that did not land. Reopened to complete missing implementation; PR 322 rollup confirms Conventional PR title, prepare, release-core-floor-smoke are the non-skipped checks.

[2026-11-03T22:07:04Z · sase-1n6.11.1] Recovery implementation: inventory schema v2 with merge_gate.required_checks [Conventional PR title, prepare, release-core-floor-smoke], digest 09ead2c4e6f8fe4ebb62581eb28dd12113ac27c1cfe509e8cdb916a07f891c67. Reader uses local validated inventory and emits source plus inventory_digest. Rust wire v2 judges Master Gate by its own nonempty all-success job list; PR requirements remain separate and fail closed. Complete sase-core check 8cf347c38da8875107dda8bddbd7a1f3 passed exit 0, including new independence and missing/non-success job tests plus existing empty/unreadable/missing/skipped PR checks. Phase remains open pending Python verification, live read-only proof and source-pin ratchet after the host commits the core changes.

[2026-11-03T22:14:49Z · sase-1n6.11.1] Recovery verification update: local install-venv e62b2e22a7c0a7ae53d9c9d008188375 passed; just fix passed. Targeted Python verification passed 166 tests across release_core, inventory, metrics, decide, health, actions and CLI, including the real wire-v2 binding using PR-only checks. Live .venv/bin/python tools/release_watch --once --json exited 0 with schema_version=2, primary=core_cut_red for macOS core-cut run https://github.com/sase-org/sase-core/actions/runs/41664195679 attempt 1, and train_action=null; no unreadable-required-checks wait. No epic-symbols. Remaining: host commits both recovered implementations, then ratchet sase-core-revision.txt to contain the new core commit, run sase tool run check, and explicitly close this reopened bead after the result is verified.

[2026-11-03T22:43:55Z · sase-1n6.11.1--1] Post-monitor verification: primary check efee02fcfdae8b2651d21656487f039b succeeded exit 0 (parent monitor ToolRun f63de0a2852a8cd0c791eb3689be16b1). However both recovered implementations are still dirty, fetched sase-core origin/master is bbef1df25612c79839e4ae96d9d5648ce041b4a8 with wire v1, and the source pin remains that old commit. Thus the first ratchet did not establish containment. Included the recovered wire.rs version bump in the pending core commit obligation, along with all other implementation files. No source bytes changed in this follow-up; prior core check 8cf347c38da8875107dda8bddbd7a1f3, targeted 166 tests, and live wire-v2 core_cut_red proof remain applicable. No epic-symbol entries. Staging a guarded post-finalization monitor that first verifies every recovered file is committed, proves the published core commit is contained by the pin (ratchets only if needed), then runs the primary check and a fresh read-only live proof. Keeping only this phase open until the resulting evidence is verified.

[2026-11-03T22:44:51Z · sase-1n6.11.1--1] Handoff cause confirmed: sase final status sase-1n6.11.1--plan reports carried_repo for both repositories, not commit receipts. Ordinary staged monitors synthesize carry declarations. This follow-up will explicitly submit commit decisions for both recovered repositories after staging the monitor, overriding that default as required by the requested host commit. The host revision_pin configuration for sase-core names sase-core-revision.txt. The monitor guard checks all 14 primary and 7 core changed files against committed HEAD blobs before accepting pin ancestry or spending time on another check.

[2026-11-03T23:35:08Z · sase-1n6.11.1--2] Recovered merge-checks implementation is committed and published: sase a732756c9eb926ee83d580d24170b65ca83e5efe; sase-core 4b1b8aca1156bf0f91dbc0fb7a33048d948f4254. Committed sase-core-revision.txt equals 4b1b8aca1156bf0f91dbc0fb7a33048d948f4254. Independently fetched both origin/master refs, verified both HEADs are published, core commit <= pin <= core origin/master with git merge-base --is-ancestor, and verified all 14 primary plus 7 core recovered file hashes against committed HEAD and working trees; both trees clean.

Landed contract: .github/release-qualification.json schema 2; merge_gate.required_checks = [Conventional PR title, prepare, release-core-floor-smoke]; inventory SHA-256 09ead2c4e6f8fe4ebb62581eb28dd12113ac27c1cfe509e8cdb916a07f891c67. Reader records source=release-qualification inventory and inventory_digest without requiring branch protection. Python mirror, Rust wire and installed release_steward_wire_schema_version() all report 2. Master Gate requires its own nonempty all-success job list; PR checks use the inventory list and remain fail-closed.

Verification: complete core check 8cf347c38da8875107dda8bddbd7a1f3 passed exit 0; targeted Python 166 passed; final primary check df54dcddede232d404e6ddc1aff450f9 passed exit 0, including its automatic full-suite escalation. Guarded monitor f30x41eynt8p (ToolRun ce1624169b9def5609fe48a8e402002e) passed exit 0. Fresh read-only --once --json returned schema_version=2, process_exit=0, primary=core_cut_red for macOS core-cut run https://github.com/sase-org/sase-core/actions/runs/41664195679 attempt 1; no unreadable-required-checks wait and no action executed. Existing macOS canary escalation #325 remains outside this phase per the epic. No --epic-symbol entries. Closing only sase-1n6.11.1; ancestor epics remain open.

## Dependencies

- **Blocks:** [sase-1n6.11.3](sase-1n6.11.3.md) ✓ · ⧖ 2026-11-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.11.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.11.1.md) | [sase-1n6.11.1](sase-1n6.11.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4b1b8ac`](https://github.com/sase-org/sase-core/commit/4b1b8aca1156bf0f91dbc0fb7a33048d948f4254) | fix(release-steward)!: separate Master Gate jobs from PR merge checks | [sase-1n6.11.1](sase-1n6.11.1.md) | 2026-11-03 17:45:40 EST |
| sase | [`a732756`](https://github.com/sase-org/sase/commit/a732756c9eb926ee83d580d24170b65ca83e5efe) | fix(release-steward): read merge checks from the versioned inventory | [sase-1n6.11.1](sase-1n6.11.1.md) | 2026-11-03 17:47:22 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.11.1--1][1] | Need phase scope, design, and recovery notes before final verification and closure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.11.1.md

<!-- sase:referenced-by:end -->
