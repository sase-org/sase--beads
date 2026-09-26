# Bead: sase-1ah.8.2 — Adopt the core report and released wheel

[Bead Pages](../README.md) / [sase-1ah.8](sase-1ah.8.md) / sase-1ah.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ah.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ah.land.md) · **Assignee:** `sase-1ah.8.2` · **Size:** medium
**Created:** 2026-09-26 13:37:31 EDT · **Closed:** 2026-09-26 17:41:32 EDT
**Plan:** [202609/e4\_landing\_remainder.md](https://github.com/sase-org/sase--plans/blob/main/202609/e4_landing_remainder.md)

## Description

python-adapter-release: replace the Python ledger and Git comparison with a thin Rust adapter, ratchet the core pin, and make fresh installs require a published receipt-capable wheel.

## Notes

[2026-09-26T21:41:00Z · sase-1ah.8.2] PROPOSED FOLLOW-UP: raise sase-core-rs floor past the receipt-report wheel + uv.lock + fresh-install verify once release-plz publishes (currently red: cargo cannot select sase_gateway ^0.34.0; PyPI latest 0.34.73/Sept-23 predates 9f86897/e654e7c/0cf5147; probe confirms tool_run_receipts_report in no release tag)

[2026-09-26T21:41:13Z · sase-1ah.8.2] PROPOSED FOLLOW-UP: just _lint-symvision fails identically on clean base (_legacy_sase_shell_syntax_enabled, _sync_scrollbar_position private-misuse); already tracked via sase-19x.11.2 and sase-19x.11.5.1 notes

[2026-09-26T21:41:32Z · sase-1ah.8.2] Adapter done: receipt_report.py is a thin tool_run_receipts_report call (764→~230 lines), CLI validation + Rich/JSON presentation retained; wrapper added in core/tool_run.py. Verified: 5 receipt-report + 17 receipt/query tests pass on the Rust core; ruff/format/mypy clean. Pin e44af7d already contains 0cf5147/e654e7c/9f86897. Wheel floor raise deferred per plan (no published wheel yet; release-plz red) as follow-up note. just check symvision fails identically on clean base (tracked sase-19x.11.2/11.5.1).

## Dependencies

- **Depends on:** [sase-1ah.8.1](sase-1ah.8.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ah.8.3](sase-1ah.8.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.8.2/README.md) | [sase-1ah.8.2](sase-1ah.8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f7886b1`](https://github.com/sase-org/sase/commit/f7886b1a64dab09bb7bc85846f6b838dd6b955bc) | feat(tool): adopt Rust core receipts opportunity report (sase-1ah.8.2) | [sase-1ah.8.2](sase-1ah.8.2.md) | 2026-09-26 17:42:59 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0sz][1] | Identify actual blockers and last progress on E4 receipt landing | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0sz/README.md

<!-- sase:referenced-by:end -->
