# Bead: sase-1ah.8.4.2 — Publish the wheel and raise the sase floor

[Bead Pages](../README.md) / [sase-1ah.8.4](sase-1ah.8.4.md) / sase-1ah.8.4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ah.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ah.8.land.md) · **Assignee:** `sase-1ah.8.4.2` · **Size:** medium
**Created:** 2026-09-26 18:37:53 EDT · **Closed:** 2026-09-27 07:31:45 EDT
**Plan:** [202609/receipt\_capable\_wheel.md](https://github.com/sase-org/sase--plans/blob/main/202609/receipt_capable_wheel.md)

## Description

ratchet-receipt-wheel: cut the urgent sase-core release, confirm a complete receipt-capable sase-core-rs wheel, and raise sase's floor with a fresh-install proof.

## Notes

[2026-09-27T10:29:25Z · sase-1ah.8.4.2--5] Published sase-core-rs 0.35.0 (release PR sase-org/sase-core#313 merged 2026-09-27T09:52:48Z, tag commit fe1e065; PyPI complete with all five EXPECTED_DIST_SUFFIXES files, none yanked). Ratchet applied via just ratchet-core-window: floor sase-core-rs>=0.35.0,<0.36.0 (pyproject.toml + uv.lock). Fresh-install proof in clean venv (PYTHONPATH/SASE_CORE_WHEEL unset, no linked-checkout override): pip resolved sase-core-rs==0.35.0 from PyPI, import lands in venv site-packages; sase tool receipt check on receipt-block catalog returns typed refusal (fingerprint_changed on dirty ratchet tree, exit 1); sase tool receipt test -j returns typed no_receipt refusal (exit 1); sase tool receipts renders full report (exit 0).

[2026-09-27T10:29:43Z · sase-1ah.8.4.2--5] PROPOSED FOLLOW-UP: tools/check_sase_core_rs_bindings reports sase_core_rs 0.35.0 missing 1 of 715 required bindings (proc_wire_schema_version); base-tree 0.34.73 is missing the same binding plus 6 more that 0.35.0 closed, so the leftover gap is pre-existing, not caused by this ratchet. Runtime is unaffected (src/sase/procs/store.py _reserve_request_schema_version falls back to PROC_WIRE_SCHEMA_VERSION on AttributeError, pending sase-1ab.8 pin-bump). CI lint step Check pinned core bindings builds from sase-core-revision.txt (e44af7d, also lacks the binding) so that step likely fails on master independent of this phase.

[2026-09-27T11:31:28Z · sase-1ah.8.4.2--6] PROPOSED FOLLOW-UP: sase tool run check c9793a40c14b05e4c6ba70e23a2f6f23 fails on base tree too — triage 46 NEW / 18 KNOWN / 1 FLAKY; lint mypy 4 KNOWN + symvision 13 KNOWN continued; scoped test lane 50 failed incl. test_submit_records_a_named_proc_and_settles_success (proc-shell vs named-proc), proc parser help, snapshot drift. Verified identical on clean base: git stash of pyproject.toml+uv.lock (floor back to >=0.34.71,<0.35.0) then pytest test_submit_records_a_named_proc_and_settles_success + test_proc_run_and_list_parse_named_named_proc + test_checked_in_snapshot_has_no_drift still fails 3/3; stash pop restores >=0.35.0,<0.36.0. Ratchet diff is floor-only, not the cause.

[2026-09-27T11:31:45Z · sase-1ah.8.4.2--6] sase-core-rs 0.35.0 published complete on PyPI (5 EXPECTED_DIST_SUFFIXES files, none yanked; tag fe1e065 descends from 0cf5147/9f86897/e654e7c, newer than 0.34.73). Ratchet via just ratchet-core-window: floor sase-core-rs>=0.35.0,<0.36.0 in pyproject.toml+uv.lock only. Fresh-venv proof (PyPI-resolved 0.35.0, no linked override): receipt check typed refusal, unrecorded tool typed no_receipt, receipts report exit 0. sase tool run check c9793a40 fails identically on clean base tree (3/3 sampled tests reproduce after stashing floor files), recorded as PROPOSED FOLLOW-UP; epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1ah.8.4.1](sase-1ah.8.4.1.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.8.4.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ah.8.4.2.md) | [sase-1ah.8.4.2](sase-1ah.8.4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bc71445`](https://github.com/sase-org/sase/commit/bc71445748c91d038e47f8473ce9d6ace1e20fc0) | chore(core): ratchet sase-core-rs floor to \>=0.35.0,\<0.36.0 | [sase-1ah.8.4.2](sase-1ah.8.4.2.md) | 2026-09-27 07:33:59 EDT |
