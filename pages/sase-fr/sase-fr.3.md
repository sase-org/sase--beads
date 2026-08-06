# Bead: sase-fr.3 — Shared reopen presentation vocabulary

[Bead Pages](../README.md) / [sase-fr](README.md) / sase-fr.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tr/README.md) · **Assignee:** `sase-fr.3` · **Size:** small
**Created:** 2026-08-05 21:19:23 EDT · **Closed:** 2026-08-05 22:53:30 EDT
**Plan:** [202608/bead\_close\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)

## Description

presentation: add sase/bead/reopen_presentation.py with the accent, glyph, section label, badge, record labels, search text, and the single shared join that decides which +1 entry reopened a bead.

## Notes

[2026-08-06T02:53:30Z · sase-fr.3] Added src/sase/bead/reopen_presentation.py with REOPEN_ACCENT/GLYPH/STYLE constants, reopen_badge, close_record_label, close_record_reopened_label (per-cause), close_history_display_order (newest-first), close_history_search_text, and the evidence_reopened_bead (reporter, timestamp) join. Whitelisted the still-unconsumed public symbols under --epic-symbol 'sase-fr(...)' in the Justfile symvision stage until the cli/triage/ace/pages phases wire them in. Added 18 unit tests in tests/test_bead/test_reopen_presentation.py covering the badge zero boundary, each reopen cause's label (including the reopened_by-absent plus_one fallback), newest-first ordering, and the join (match, wrong reporter, wrong timestamp, empty history, non-plus-one cause). Verified: just lint (ruff, mypy, symvision, toobig) clean; just check test suite green except test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget, which fails only under full-suite sandbox contention and passes in isolation (23.46s), confirmed unrelated to this change.

[2026-08-06T02:54:17Z · sase-fr.3] Verified: bead already closed locally in prior session (reopen_presentation.py + tests + Justfile symvision whitelist); re-running close to confirm publish status.

## Dependencies

- **Depends on:** [sase-fr.2](sase-fr.2.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fr.4](sase-fr.4.md) ◐ · ⧖ 2026-08-05
- **Blocks:** [sase-fr.5](sase-fr.5.md) ◐ · ⧖ 2026-08-05
- **Blocks:** [sase-fr.6](sase-fr.6.md) ◐ · ⧖ 2026-08-05
- **Blocks:** [sase-fr.7](sase-fr.7.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.3/README.md) | [sase-fr.3](sase-fr.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9d0422f`](https://github.com/sase-org/sase/commit/9d0422fdacd5d64144885212bbbe5515b7c62a03) | feat(bead): add shared reopen presentation vocabulary | [sase-fr.3](sase-fr.3.md) | 2026-08-05 22:54:54 EDT |
