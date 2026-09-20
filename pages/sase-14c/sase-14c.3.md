# Bead: sase-14c.3 — Default header indicator policy

[Bead Pages](../README.md) / [sase-14c](README.md) / sase-14c.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0o6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0o6.md) · **Assignee:** `sase-14c.3` · **Size:** small
**Created:** 2026-09-20 12:41:11 EDT · **Closed:** 2026-09-20 16:00:18 EDT
**Plan:** [202609/muse\_usage\_windows.md](https://github.com/sase-org/sase--plans/blob/main/202609/muse_usage_windows.md)

## Description

indicator-default: ship default config that shows only Muse's weekly window in the TUI header usage cluster, document it, and verify the rendered result.

## Notes

[2026-09-20T19:59:46Z · sase-14c.3] PROPOSED FOLLOW-UP: master `just check` is red independent of sase-14c — flags gate rule 7 (closed sase-12m still has service_host), symvision stale --epic-symbol sase-14d.4 entries in Justfile, and 7 failing tests (tests/test_capacity_gate_to_admission.py x2, tests/ace/tui/test_epic_panel_arrival_frames.py x4, tests/ace/tui/test_lazy_tier2_reconcile_apply.py x1) fail identically on a clean tree

[2026-09-20T20:00:18Z · sase-14c.3] Added muse.windows.session: never to default_config.yml and schema default; weekly window selected by weekly_all via phase-1 classification. Documented in docs/configuration.md and docs/llms.md. New tests: shipped defaults select Muse weekly/reject session, generic fallback restored without override, installed-only eligibility pin, real-header render at 60/80/140 (test_usage_header). Verified dark+light segment rendering with the ♾️ badge; live 'sase usage refresh -p muse' landed both windows via probe. No layout change, so no PNG goldens changed. just check stops on pre-existing unrelated failures (flags sase-12m, symvision sase-14d.4, 7 tests failing on clean tree); ruff/mypy/fmt/keep-sorted pass.

## Dependencies

- **Depends on:** [sase-14c.2](sase-14c.2.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14c.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14c.3/README.md) | [sase-14c.3](sase-14c.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ec7dbbf`](https://github.com/sase-org/sase/commit/ec7dbbfdf97ce5341d9f0247cbfff50e32482de2) | feat(usage): hide Muse's 5-hour window from the header by default | [sase-14c.3](sase-14c.3.md) | 2026-09-20 16:01:38 EDT |
