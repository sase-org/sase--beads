# Bead: sase-1s7.1 — The deterministic reds on master are fixed

[Bead Pages](../README.md) / [sase-1s7](README.md) / sase-1s7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1b0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1b0.md) · **Assignee:** `sase-1s7.1` · **Size:** medium
**Created:** 2026-11-10 14:38:15 EST · **Closed:** 2026-11-10 15:23:52 EST
**Plan:** [202611/ci\_green\_v0\_19\_0\_pypi\_release.md](https://github.com/sase-org/sase--plans/blob/main/202611/ci_green_v0_19_0_pypi_release.md)

## Description

master-reds: fix the test_core_rust monkeypatch ordering, the coverage-contexts crash from a global os.stat patch, and the Archive golden drift from the focus change, plus any other deterministic red at the tip.

## Notes

[2026-11-10T20:23:52Z · sase-1s7.1--1] Fixed the Rust monkeypatch ordering and scoped the plan-render os.stat guard to the caller. Updated 15 Archive and Record goldens for Archive list focus; visual fixtures now focus the list explicitly for stable captures. The focused TZ=UTC snapshot check passed twice (21 cases each, zero unstable nodes); just fix passed; ToolRun 5b482a9a32fcabaf6aba8d12b141c0fb (sase tool run check) passed with exit 0. sase-1s6 is resolved by the monkeypatch reorder; only sase-1s7.1 is closed here.

## Dependencies

- **Blocks:** [sase-1s7.4](sase-1s7.4.md) ◐ · ⧖ 2026-11-10
- **Blocks:** [sase-1s7.5](sase-1s7.5.md) ◐ · ⧖ 2026-11-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1s7.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1s7.1.md) | [sase-1s7.1](sase-1s7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1df3ade`](https://github.com/sase-org/sase/commit/1df3ade04d8fe9c315d5491c816b9b46f21967cf) | fix(ci): clear master reds and stabilize archive goldens | [sase-1s7.1](sase-1s7.1.md) | 2026-11-10 15:25:38 EST |
