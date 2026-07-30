# Bead: sase-ar — AXE Chop Reports

[Bead Pages](../README.md) / sase-ar

**Status:** ✓ closed · **Resolution:** done · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ar.land`
**Created:** 2026-07-29 13:49:51 UTC · **Closed:** 2026-07-29 15:40:51 UTC
**Plan:** [202607/axe\_chop\_reports.md](https://github.com/sase-org/sase--plans/blob/main/202607/axe_chop_reports.md)

## Description

Selecting a chop on the ACE AXE tab shows a beautiful, colored, width-responsive report of that run — a universal result card for every chop plus an optional chop-authored report document — and all four bugyi-chops scripts publish rich reports of their own.

## Notes

[2026-07-29T15:40:51Z · sase-ar.land] Verified all six phases against source, not just phase notes. Rust contract lives in sase-core (ChopReportWire/ChopReportBlockWire 8 kinds/ChopReportToneWire 7 tones, deny_unknown_fields, 32 KiB cap, glyph allowlist, fail-closed validation); SDK ChopReport/Tone builder with normalization and bounds exported from sase.chops; chop_report_render.py tone-to-style map with narrow stacking, numeric right-align, cell elision and gauge clamping; _axe_chop_result_card.py RESULT card cached on (lumberjack, chop, run_id, status, finished_at, width) with the terminal-run scroll fix in axe_display/_render.py; CLI reuse via chop_render.py; 4 new PNG goldens plus 2 refreshed; bugyi-chops _report.py house style with ci_watch/toobig_split/recent_audits reports, toobig_split clan summary and report both projected from the shared _target_rows ledger, and check_error/no-op paths carrying reports. Ran an end-to-end smoke through SDK build -> Rust validate_chop_report -> renderer. just check passes fmt, keep-sorted, ruff, mypy, pyscripts, symvision, toobig and tests.

Integration since the epic started: bumped sase-core-rs from >=0.12.8 to >=0.12.9 in pyproject.toml and refreshed uv.lock (which still pinned 0.12.5). The report wire shipped in sase-core v0.12.9, published 2026-07-29T14:24Z after the contract phase closed, so this could not be done earlier; v0.12.8's ChopResultDocumentWire is deny_unknown_fields with no report field, meaning any non-dev install would have rejected every report-bearing chop result at parse time. Added the missing PROMPT backlink to the epic plan file, clearing its 2 plan-links validation errors. Reviewed all post-epic commits: sase-at.1's notifications/report.py correctly consumes this epic's validate_chop_report with no duplicate renderer or tone map, bugyi-chops 4f4fdd6 already builds a ChopReport downstream, and sase-as.1's copy-mode edit to axe_display/_render.py touches only the footer branch and coexists with the epic's scroll fix.

Outstanding follow-up, not fixable here: bugyi-chops pins sase>=0.13.2,<0.14.0 but ChopReport landed after the sase 0.13.2 release, so the honest floor is the next sase release (0.13.3+) and that bump is blocked on publishing sase.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-ar.1](sase-ar.1.md) | Chop report document in the Rust core | ✓ closed | medium | 1 | 1 |
| [sase-ar.2](sase-ar.2.md) | ChopReport builder in the sase.chops SDK | ✓ closed | medium | 1 | 1 |
| [sase-ar.3](sase-ar.3.md) | AXE chop-run result card and report rendering | ✓ closed | medium | 1 | 1 |
| [sase-ar.4](sase-ar.4.md) | PNG snapshot coverage for chop reports | ✓ closed | small | 1 | 1 |
| [sase-ar.5](sase-ar.5.md) | Reports for every bugyi-chops chop | ✓ closed | medium | 1 | 0 |
| [sase-ar.6](sase-ar.6.md) | End-to-end verification on the real AXE tab | ✓ closed | small | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ar: AXE Chop Reports [closed]"]
    n1["sase-ar.1: Chop report document in the Rust core [closed]"]
    n2["sase-ar.2: ChopReport builder in the sase.chops SDK [closed]"]
    n3["sase-ar.3: AXE chop-run result card and report rendering [closed]"]
    n4["sase-ar.4: PNG snapshot coverage for chop reports [closed]"]
    n5["sase-ar.5: Reports for every bugyi-chops chop [closed]"]
    n6["sase-ar.6: End-to-end verification on the real AXE tab [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n1 -.-> n3
    n2 -.-> n5
    n3 -.-> n4
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ar.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ar.1/README.md) | [sase-ar.1](sase-ar.1.md) | 1 |
| [bbugyi200.athena.sase-ar.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ar.2/README.md) | [sase-ar.2](sase-ar.2.md) | 1 |
| [bbugyi200.athena.sase-ar.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ar.3/README.md) | [sase-ar.3](sase-ar.3.md) | 1 |
| [bbugyi200.athena.sase-ar.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ar.4/README.md) | [sase-ar.4](sase-ar.4.md) | 1 |
| [bbugyi200.athena.sase-ar.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ar.5/README.md) | [sase-ar.5](sase-ar.5.md) | 0 |
| [bbugyi200.athena.sase-ar.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ar.6/README.md) | [sase-ar.6](sase-ar.6.md) | 0 |
| [bbugyi200.athena.sase-ar.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ar.land/README.md) | [sase-ar](README.md) | 2 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@4419772`](https://github.com/sase-org/sase-core/commit/441977217d00fb5d4589a09e04ae3db72d536159) | feat(axe): add structured chop report contract | [sase-ar.1](sase-ar.1.md) | 2026-07-29 13:59:59 |
| [`bc501e5`](https://github.com/sase-org/sase/commit/bc501e595b0ee0e09d915daf68b7528b1bc50a84) | feat(axe): render structured chop result reports | [sase-ar.3](sase-ar.3.md) | 2026-07-29 14:27:59 |
| [`5885890`](https://github.com/sase-org/sase/commit/58858901b857cfb9b3831cb61bb8c00e1bfbfd78) | feat(chops): add typed report builder | [sase-ar.2](sase-ar.2.md) | 2026-07-29 14:30:54 |
| [`8700173`](https://github.com/sase-org/sase/commit/8700173d89e028cc8a6dac71d63a3de6feefc969) | test: add AXE chop report visual snapshots | [sase-ar.4](sase-ar.4.md) | 2026-07-29 14:59:31 |
| [`17fc09c`](https://github.com/sase-org/sase/commit/17fc09cdc0124036ed3b301bcb2031a2df11392b) | build(deps): require sase-core-rs\>=0.12.9 for the chop report wire | [sase-ar](README.md) | 2026-07-29 15:42:39 |
| [`sase--plans@a40a70d`](https://github.com/sase-org/sase--plans/commit/a40a70dc007d7955d234b86252e7975f514afe03) | Complete SDD plan for axe\_chop\_reports | [sase-ar](README.md) | 2026-07-29 15:43:26 |
