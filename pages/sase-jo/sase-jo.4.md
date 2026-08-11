# Bead: sase-jo.4 — Timeline, legend, and detail rendering

[Bead Pages](../README.md) / [sase-jo](README.md) / sase-jo.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xv](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xv/README.md) · **Assignee:** `sase-jo.4` · **Size:** medium
**Created:** 2026-08-11 06:59:09 EDT · **Closed:** 2026-08-11 08:51:17 EDT
**Plan:** [202608/stitch\_origin\_badges.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_origin_badges.md)

## Description

render: add the shared origin glyph/label/style module, the fixed origin column on timeline rows, the adaptive legend key, the Origin line in the Stitches detail panel, and the origin field in every `sase stitch log` output format, with unit and PNG visual coverage.

## Notes

[2026-08-11T12:41:29Z · sase-jo.4] PROPOSED FOLLOW-UP: Fix pre-existing Ruff formatting drift in tests/test_external_mirror_issues.py — just check currently stops on two long read_mirror_state(...) lines outside the stitch-origin rendering diff.

[2026-08-11T12:51:17Z · sase-jo.4] Verified origin render/core work with Rust VCS-log lib/parity/PyO3 tests, focused Python core/render/TUI tests, visual PNG comparison, Ruff/mypy/Symvision/lint gates, and full non-visual pytest; just check rerun is blocked only by unrelated pre-existing Ruff formatting in tests/test_external_mirror_issues.py, noted as PROPOSED FOLLOW-UP.

[2026-08-11T12:52:27Z · sase-jo.4] Verified origin rendering implementation with Rust VCS-log tests, focused Python render/TUI tests, visual PNG comparison, mypy, Ruff, Symvision, and full non-visual pytest lane; just check remains blocked by unrelated Ruff format drift recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-jo.3](sase-jo.3.md) ✓ · ⧖ 2026-08-11
- **Blocks:** [sase-jo.6](sase-jo.6.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jo.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jo.4/README.md) | [sase-jo.4](sase-jo.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`29af892`](https://github.com/sase-org/sase/commit/29af892b857c6a70ec4ba87abc17971f083ed040) | feat(vcs-log): render commit origin in timelines | [sase-jo.4](sase-jo.4.md) | 2026-08-11 08:55:51 EDT |
