# Bead: sase-1sd.5 — Stop host completion from refusing checks that passed (sase-1qm)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.5` · **Size:** large
**Created:** 2026-11-12 05:26:16 EST · **Closed:** 2026-11-12 15:13:44 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

fingerprint-refusal: prepared completions backed by a fully green just check are refused with stale_worktree_fingerprint even when every observed fingerprint matches on hand audit (5 refusals in October, 11 so far in November; fresh sase recurrences 11-07 and 11-10). Diff the sealed observation against the host-time observation for the fresh repro runs (suspect: cross-repo scope over main plus sase-core), fix the confirmed mechanism, and make every refusal record name which fingerprint component differed. Needs sase-core and sase changes.

## Notes

[2026-11-12T17:23:42Z · sase-1sd.5] PLANNING EVIDENCE: On athena at sase 1087ccd7f1 / core fae59b46, fresh same-epic monitor 3sefkg2pq2cg (sase-1sd.2--mon, 2026-11-12) passed just check in 698s but recovered for stale_worktree_fingerprint. Its intent file:explicit:3f2c9d9307bdb16af7458018 decides only main. Starter run 20261112052955 has an empty main baseline; monitor 20261112063549 freshly captured all three authored paths as pre-existing dirt. All three XY/hash pairs and baseline HEAD match the sealed intent. Pure binding replay is eligible with sealed observations and ineligible after changing only protected/foreign flags to the monitor-derived values. Source trace: monitor/member.py -> turns/member.py omits prev_artifacts_dir when calling create_followup_artifacts; baseline inheritance receives None and captures fresh dirt. Host-time observations were not retained, so this is a recorded-baseline replay, not an exact historical host snapshot. Existing core 9e1ac1da already scopes fingerprints to decided repositories. Preparing a medium tale to thread authoritative predecessor context before seeding, preserve linked obligations, and add Rust mismatch diagnostics carried into receipts/prompts. No implementation changes yet.

[2026-11-12T18:32:20Z · sase-1sd.5] IMPLEMENTATION EVIDENCE (final checks pending): Base was sase 1087ccd7f1 and core fae59b46. Monitor creation now passes the resolved starter artifacts directory into existing followup baseline inheritance; the lifecycle regression keeps new main and opened linked edits unprotected, preserves genuinely pre-existing linked dirt as protected/foreign, shows both authored paths in current finalizer obligations, evaluates the unchanged main intent as eligible, and commits only the authored paths through the real controller. Rust completion evaluation now returns bounded deterministic component diagnostics with an empty serde default; PyO3 and Python carry them into the durable recovery receipt and bounded prompt details, with legacy receipt wording covered. Historical checks reviewed: 3sefkg2pq2cg reproduces the baseline-protection mechanism on recorded inputs; enf0k7gv43fc, 4ry4tgt9j08t (member 19b--mon-0), b2ynhwznjahm, p0zxjxcyb4b6, and q277j9348xd0 all exited 0 but recovered for stale_worktree_fingerprint. Their sealed inputs show one main-plus-sase-core decision and the others main-only; the old host-time observation pair was not preserved, so those exact mismatches remain unknown. Focused verification passed: 23 Python tests across monitor recovery/prompt, monitor inheritance/finalization, and prepared declaration installation; core fingerprint_diagnostics tests; core PyO3 continuation tests. Required primary and core just check runs remain pending.

[2026-11-12T20:13:30Z · sase-1sd.5--7] FINAL VERIFICATION: Primary sase check passed (ToolRun 71c9cb0e96b107aa5be6e7fd00c053bf; monitor pdk21j6f4m3m). Linked sase-core just check passed (ToolRun 0bbfaa97a9861c8e6e5e2e3bab5de65a; monitor t1m50k08pwfs). Core HEAD fae59b46a9db7e7c37656bea7d1e7fa98ebaabc6 matches the primary sase-core-revision.txt pin. The older refusal records lack host-time observations, so their exact fingerprint differences remain unknown. No --epic-symbol entries for sase-1sd.5. reported no --epic-symbol entries.

[2026-11-12T20:13:44Z · sase-1sd.5--7] TASK RESOLVED: sase-1qm

## Dependencies

- **Depends on:** [sase-1sd.4](sase-1sd.4.md) ✓ · ⧖ 2026-11-12
- **Blocks:** [sase-1sd.6](sase-1sd.6.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sd.5.md) | [sase-1sd.5](sase-1sd.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6111b9b`](https://github.com/sase-org/sase-core/commit/6111b9b57f30663b5dd92ca7b2550e8e0c1e15ea) | feat(continuation): report fingerprint mismatch details | [sase-1sd.5](sase-1sd.5.md) | 2026-11-12 15:16:01 EST |
