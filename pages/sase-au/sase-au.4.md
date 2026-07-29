# Bead: sase-au.4 — XPrompts sub-tab with four grouping strategies

[Bead Pages](../README.md) / [sase-au](README.md) / sase-au.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-au.4` · **Size:** medium
**Created:** 2026-07-29 16:26:30 UTC · **Closed:** 2026-07-29 17:11:02 UTC
**Plan:** [202607/xprompt\_statistics.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_statistics.md)

## Description

tui-view: register the XPrompts view in the Statistics pane, render its four `g` grouping strategies with legends and honest empty states, and make the tab strip fit nine tabs at narrow widths.

## Notes

[2026-07-29T17:11:02Z · sase-au.4] Implemented the ninth Statistics XPrompts view with usage/model/project/pairing groupings, legends, unavailable/no-reference/truncation states, display-name project cells, no-query g cycling, and a compact nine-tab strip with correct hit ranges. Verified 55 focused Statistics tests; repository-wide just test reached 23,723 passed and 7 skipped with only 11 intentional Statistics PNG mismatches, then all 11 refreshed goldens passed exact visual comparison. just check passed fmt, Ruff, mypy, pyscripts, changelog, symvision, and toobig; aggregate SDD validation remains blocked only by the unrelated 202607/artifact_refs_and_prompt_bar.md prompt-link error. Also repaired this epic design's own missing PROMPT reverse link.

[2026-07-29T17:12:17Z · sase-au.4] Verified 55 focused Statistics tests, exact comparison for all 11 Statistics visual snapshots after reviewed golden updates, broad suite with 23,723 passing and 7 skipped aside from those intentional pre-refresh goldens, plus clean formatting, Ruff, mypy, and Symvision gates; aggregate just check remains blocked only by an unrelated concurrent SDD prompt-link diagnostic.

## Dependencies

- **Depends on:** [sase-au.3](sase-au.3.md) ✓
- **Blocks:** [sase-au.5](sase-au.5.md) ✓
