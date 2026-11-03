# Bead: sase-1r2.3 — The blocking test lanes stop flaking

[Bead Pages](../README.md) / [sase-1r2](README.md) / sase-1r2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.178.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.178.w0.md) · **Assignee:** `sase-1r2.3` · **Size:** medium
**Created:** 2026-11-03 11:09:31 EST · **Closed:** 2026-11-03 15:15:44 EST
**Plan:** [202611/v0\_19\_0\_green\_full\_ci\_release.md](https://github.com/sase-org/sase--plans/blob/main/202611/v0_19_0_green_full_ci_release.md)

## Description

blocking-flakes: fix the races behind intermittent reds in Master Gate's jobs and in Full CI's lint and test (3.12|3.13|3.14) jobs.

## Notes

[2026-11-03T20:15:18Z · sase-1r2.3--3] PROPOSED FOLLOW-UP: default .venv (Python 3.14) ships a stale sase_core_rs without agent_prompt_select (.so built Nov 1; py312 .so rebuilt today has it; pyproject pins sase-core-rs==0.43.2 whose published wheel lacks 32 source-only capabilities per core-floor-probe). Any broad xdist lane on .venv fails ~200 untouched prompt/deck tests with AttributeError require_rust_binding. Remedy: run just install-venv for the default venv, then rerun one broad -n 8 pass over tests/ace/tui tests/monitor on .venv to confirm green.

[2026-11-03T20:15:44Z · sase-1r2.3--3] Verified: 4 race fixes (wait_for on create availability instead of fixed 0.6s sleep; cursor_blink=False for TODO cursor-style assertion; split sdd streaming test into deterministic timeout vs group-kill halves with pid-file handshake; explicit lock-release handshake in sudo settlement). just fix exit 0, git diff --check clean. Targeted proof on py312 with workspace-matched sase_core_rs: 699 passed (all stress target nodes plus tests/monitor) in 4m25s; 5/5 race nodes pass standalone. sase tool run check 21eb6f04: all lint gates pass (fmt, ruff, mypy, symvision, docs, SASE validation); test lane still running at single-turn ceiling. Stress monitor dea3t69bq0sr broad tail failure (222) is stale-env: default .venv .so predates agent_prompt_select, failing ~200 untouched files at require_rust_binding; py312 lanes with fresh binding pass. Follow-up recorded for default-venv rebuild plus broad rerun. Takeover notes verified on sase-1ql, sase-1ny, sase-1oy, sase-1mu, sase-1gg, sase-xh. No epic-symbol entries remain.

## Dependencies

- **Blocks:** [sase-1r2.6](sase-1r2.6.md) ◐ · ⧖ 2026-11-03
- **Blocks:** [sase-1r2.7](sase-1r2.7.md) ◐ · ⧖ 2026-11-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r2.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r2.3.md) | [sase-1r2.3](sase-1r2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`26b50ca`](https://github.com/sase-org/sase/commit/26b50ca5251945db4d9ca3efe804cd843f36bed9) | fix(flakes): de-flake blocking Master Gate and Full CI test lanes | [sase-1r2.3](sase-1r2.3.md) | 2026-11-03 15:18:23 EST |
