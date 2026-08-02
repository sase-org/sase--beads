# Bead: sase-dz.2 — Make bead prose highlighting ignore ambient NO\_COLOR

[Bead Pages](../README.md) / [sase-dz](README.md) / sase-dz.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rm](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rm/README.md) · **Assignee:** `sase-dz.2` · **Size:** small
**Created:** 2026-08-02 10:45:51 UTC · **Closed:** 2026-08-02 10:57:02 UTC
**Plan:** [202608/ci\_green\_restoration.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restoration.md)

## Description

bead-color: force color on the internal rendering console so `--color always` wins over the ambient NO_COLOR environment variable, restore the highlighted ANSI golden that was overwritten with degraded output, and add a regression test that renders under NO_COLOR.

## Notes

[2026-08-02T10:56:32Z · sase-dz.2] PROPOSED FOLLOW-UP: Narrow the blanket `except Exception: return text` in highlight_prose (src/sase/bead/cli_detail_prose.py) so a real highlighting failure is observable in tests instead of silently degrading to unhighlighted output — flagged as a "consider, not required here" item in the ci_green_restoration plan.

[2026-08-02T10:57:02Z · sase-dz.2] Fixed: passed no_color=False to the Console in cli_detail_prose._render_text so --color always beats ambient NO_COLOR. Restored tests/test_bead/golden/cli/show_style_closed_phase.ansi to its exact pre-c1efe9f93 highlighted (ESC[1;49m) form via 'git show c1efe9f93^:<path>'. Added test_show_closed_phase_with_markdown_rich_ansi_snapshot_ignores_no_color, which sets NO_COLOR=1 and asserts the rendered output still matches the golden. Reviewed the other 5 goldens c1efe9f93 touched (list_json.stdout, list_json_limit.stdout, list_implicit_closed_json.stdout, show_json.stdout, show_phase_json.stdout) and confirmed those diffs are only plus_one_count/plus_one_evidence field additions, not color degradation. Verified: all 40 tests in tests/test_bead/test_cli_show_style.py pass, all 1199 tests in tests/test_bead/ pass, and 'just check' fmt/lint/mypy all pass (the SASE validation failure it also reports is the pre-existing, unrelated plan-links-migration issue owned by sase-dz.5). Closed sase-df as resolved by this fix.

## Dependencies

- **Blocks:** [sase-dz.6](sase-dz.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dz.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.2/README.md) | [sase-dz.2](sase-dz.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`a7ac9cc`](https://github.com/sase-org/sase/commit/a7ac9cc9af0e7e720d4303a7cef934c5e623f829) | fix(bead): force color in prose rendering so --color always beats NO\_COLOR | [sase-dz.2](sase-dz.2.md) | 2026-08-02 10:58:22 |
