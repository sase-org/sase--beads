# Bead: sase-1my.2 — Family install canary on Linux and macOS

[Bead Pages](../README.md) / [sase-1my](README.md) / sase-1my.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11s](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11s.md) · **Assignee:** `sase-1my.2` · **Size:** medium
**Created:** 2026-10-19 10:16:27 EDT · **Closed:** 2026-10-19 10:39:37 EDT
**Plan:** [202610/e1\_installable\_family.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_installable_family.md)

## Description

canary: extend install-smoke.yml to install sase plus the plugins on ubuntu and macOS, assert newest and exact versions, run the first commands, publish a result artifact, and open or close one alert issue.

## Notes

[2026-10-19T14:39:37Z · sase-1my.2] Canary live: install-smoke.yml is now a ubuntu+macos matrix (fail-fast false) running the single-sourced documented + family commands in isolated tool dirs with cache off; helper tools/check_family_install asserts newest/exact per package and window rule for sase-core-rs, writes install-canary-<os>.json, proves plugin entry points; alert job holds the only issues:write and opens/comments/closes one install-canary issue (probes stay quiet without alert=true). Verified: 35 tests pass (15 helper incl. 0.1.0-red/yanked-ignored/window-green/backtrack-red, 12 workflow contract, 8 render_applicability incl. existing suite green), sase tool run check green, plus live runs on athena — isolated family install GREEN (sase 0.18.0, plugins, core 0.42.1 window), probe sase==99.0 RED with expected reason, exact reinstall GREEN, completion/doctor/health/plugin-proof all ok. No epic-symbol leftovers. First scheduled live run left to exit phase.

## Dependencies

- **Blocks:** [sase-1my.5](sase-1my.5.md) ◐ · ⧖ 2026-10-19
- **Blocks:** [sase-1my.6](sase-1my.6.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1my.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1my.2/README.md) | [sase-1my.2](sase-1my.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6a0090f`](https://github.com/sase-org/sase/commit/6a0090f0d90008a4ad382a608dc2196eed63813d) | feat(install): add family install canary workflow and checks | [sase-1my.2](sase-1my.2.md) | 2026-10-19 10:41:36 EDT |
