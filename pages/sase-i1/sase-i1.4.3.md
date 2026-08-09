# Bead: sase-i1.4.3 — Adopt the corrected core release and verify both lanes

[Bead Pages](../README.md) / [sase-i1.4](sase-i1.4.md) / sase-i1.4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-i1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.land/README.md) · **Assignee:** `sase-i1.4.3` · **Size:** medium
**Created:** 2026-08-09 09:05:46 EDT · **Closed:** 2026-08-09 10:12:09 EDT
**Plan:** [202608/bead\_search\_regex\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_search_regex_landing.md)

## Description

adopt-corrected-release: wait for the corrective core release, raise the floor, add cross-format integration coverage, and run exhaustive verification.

## Notes

[2026-08-09T14:11:34Z · sase-i1.4.3] PROPOSED FOLLOW-UP: Refresh home memory/provider shims — after this phase, `just check-full` reaches `sase validate` and fails only because `init memory --check` wants to overwrite ~/.local/share/chezmoi/home/AGENTS.md plus CLAUDE.md, GEMINI.md, QWEN.md, and OPENCODE.md (+2/-2 each); phase worker did not run `sase memory init` because no user memory-update permission was granted.

[2026-08-09T14:12:09Z · sase-i1.4.3] Merged and verified the corrective core release: sase-core PR #100 landed as c8c1f2c, tag v0.21.3 contains matcher fix 49650a0, release workflow 31316267135 completed green, and PyPI exposes five sase-core-rs 0.21.3 artifacts. Raised sase-core-rs floor to >=0.21.3,<0.22.0 and refreshed uv.lock. Added entrypoint integration coverage for invalid regex errors and zero-width regex matching across compact/json fast path plus full Python fallback, updated the telemetry minimum assertion, and aligned a prompt-glossary test fixture with the current display_aliases model so the exhaustive suite can run. Verified: exact published-wheel smoke with uv pip install sase-core-rs==0.21.3 exercises bead_search(..., regex=True), ^ zero-width matching, literal matching, and invalid search regex text; tools/smoke_sase_core_rs_telemetry --print-minimum reports 0.21.3; tools/validate_sase_core_rs_version --published-minimum passes; just install rebuilds local sase_core_rs 0.21.3; focused pytest for bead search, fast path, facade, project delegation, and telemetry smoke passes 61 tests; full just test passes 27935 passed, 10 skipped. just check-full was attempted twice: first reached pytest and found the unrelated prompt-glossary fixture issue fixed here; second passed fmt/lint/mypy/symvision/toobig before stopping at SASE validation because home memory/provider shims need regeneration, recorded separately as PROPOSED FOLLOW-UP on this bead because this phase had no user permission to run sase memory init.

[2026-08-09T14:14:50Z · sase-i1.4.3] Verified core release v0.21.3 contains matcher fix 49650a0; raised sase-core-rs floor/lock to 0.21.3; added search entrypoint regressions; exact wheel smoke passed; focused pytest 61 passed; just test 27935 passed, 10 skipped; just check-full blocked by out-of-scope home memory/provider shim drift recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-i1.4.1](sase-i1.4.1.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-i1.4.2](sase-i1.4.2.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i1.4.4](sase-i1.4.4.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i1.4.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.4.3/README.md) | [sase-i1.4.3](sase-i1.4.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d7e9ae8`](https://github.com/sase-org/sase/commit/d7e9ae8ae5ebcc9b55d68bfa8cc739c4a550a977) | fix(search): require corrected core matcher release | [sase-i1.4.3](sase-i1.4.3.md) | 2026-08-09 10:16:12 EDT |
