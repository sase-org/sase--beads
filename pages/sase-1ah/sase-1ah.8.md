# Bead: sase-1ah.8 — Complete E4 receipt reporting and live acceptance

[Bead Pages](../README.md) / [sase-1ah](README.md) / sase-1ah.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ah.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ah.land.md) · **Assignee:** `sase-1ah.8.land`
**Created:** 2026-09-26 13:37:28 EDT · **Closed:** 2026-09-27 07:55:42 EDT
**Plan:** [202609/e4\_landing\_remainder.md](https://github.com/sase-org/sase--plans/blob/main/202609/e4_landing_remainder.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/e4_landing_remainder.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/e4_landing_remainder.md

<!-- sase:links:end -->

## Description

Move receipt opportunity facts into the Rust core, require a released receipt-capable core before a fresh install can load the catalog, and prove prepared completion on athena.

## Notes

[2026-09-26T22:03:13Z · sase-1ah.8.3] Phase 8.3 live acceptance in progress: focused Rust+Python receipt suites green (13+2 core, 19 Python), just fix clean, host ledger shows versioned no_receipt refusals and 29 repeat groups / 10.91h with zero retained receipts; full just check runs as a verify monitor (long gate) whose follow-up mints/confirms the pass receipt and closes 8.3. Remaining limits: published-wheel floor raise (8.2 follow-up), sase-19x symvision exemptions, stale no-new monitor test import (8.3 follow-up).

[2026-09-26T22:34:27Z · sase-1ah.8.land] Landing audit before the published-wheel remainder. Verified in source: sase-core 0cf5147 implements tool_run_receipts_report and the PyO3 binding; later core commits do not edit that file; pin e44af7d contains 0cf5147, 9f86897, and e654e7c. sase f7886b1a6 makes receipt_report.py a thin adapter over tool_run_receipts_report. Commits after f7886b1a6 (0a74b4f25, acbd5999a) do not touch receipt code, so there is no integration edit. No --epic-symbol entries for this epic.

The published-wheel goal is not done. PyPI is still sase-core-rs 0.34.73, which lacks the binding, and pyproject.toml is still >=0.34.71,<0.35.0. release-plz run 36272464168 fails selecting sase_gateway ^0.34.0 when the next version is 0.35.0. That remainder is a child plan, not a close.

Follow-ups from the phase notes, and why each was not a new task: the wheel floor stays epic work (child plan) and was also recorded as a +1 on standing task sase-10d. symvision private import _legacy_sase_shell_syntax_enabled and _sync_scrollbar_position are already fixed on current master (public legacy_sase_shell_syntax_enabled imported from _settings_system.py; public sync_scrollbar_position imported from panel_transitions.py). test_no_new_receipt.py's sase.shells.followup import and the proc lifecycle named-proc versus proc-shell fixture are caused by in-progress epic sase-1ab and already noted there; corroborated, no task. The sase-1ah.8.1 clean-base symvision and memory-check list was not re-run and is not caused by this epic; those symbols now have in-tree callers and open symvision tasks already exist, so no new bead. Live accept:pass was not minted; just check stays red on the sase-1ab failures, and phase 8.3 recorded the 2026-09-26 owner check (next due 2026-10-10). That demonstration is not this epic's remaining code.

[2026-09-27T11:55:42Z · sase-1ah.8.4.land] Rechecked after child epic sase-1ah.8.4 closed. The prior landing note (#2) named one remaining gap: the published receipt-capable wheel. That is now done: sase-core-rs 0.35.0 (tag v0.35.0, fe1e065, which contains 0cf5147/9f86897/e654e7c) is complete on PyPI, and sase bc7144574 raised the floor to >=0.35.0,<0.36.0 with a fresh-venv PyPI-wheel proof (the receipt: catalog loads, receipt check/test give typed refusals, receipts exits 0). All descendants are closed: 8.1, 8.2, 8.3, and child epic 8.4. Drift: no commits after f7886b1a6 touch src/sase/tool, sase/sase.yml, or the receipt adapter, so no integration edit was needed. Epic-symbols: none. Remaining limitation, carried over from phase 8.3 and accepted by plan phase 3's 'record remaining limitation' clause: no live accept:pass receipt was minted, because just check is still red on active epic sase-1ab's rename drift (recorded there as DISCOVERED ISSUEs, including the proc_wire_schema_version binding gap). The owner check is dated 2026-09-26, next due 2026-10-10. Phase follow-ups were already routed by the prior landing (sase-10d +1, sase-1ab corroboration, existing symvision beads).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ah.8.land.md) | [sase-1ah.8](sase-1ah.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0sz][1] | Find each epic status, child phase, notes, and blockers for the requested stall report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0sz/README.md

<!-- sase:referenced-by:end -->
