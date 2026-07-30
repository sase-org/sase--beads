# Bead: sase-bf.2 — Full JSON output-variable values in the sase-core scan wire

[Bead Pages](../README.md) / [sase-bf](README.md) / sase-bf.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bf.2` · **Size:** medium
**Created:** 2026-07-30 21:00:26 UTC · **Closed:** 2026-07-30 21:09:41 UTC
**Plan:** [202607/structured\_sase\_variables.md](https://github.com/sase-org/sase--plans/blob/main/202607/structured_sase_variables.md)

## Description

core-wire-json: generalize OutputVariableValue in the sase-core agent-scan wire from text-or-string-list to a bounded JSON value, release sase-core, bump the sase-core-rs pin here, and widen the Python wire marker type.

## Notes

[2026-07-30T21:59:00Z · sase-bf.2] Verified sase-core with cargo fmt --all -- --check, cargo test --workspace, and cargo clippy --workspace --all-targets -- -D warnings; released v0.16.0 through release-plz and confirmed the complete GitHub/PyPI workflow; verified the Python v0.16.0 install, published-minimum guard, uv lock, 15 focused scan/index/wire/version tests, and all formatter/linter gates. Full Python run reached 24,503 passing tests with one unrelated ACE visual contention timeout that passed in isolation; just check is otherwise blocked only by pre-existing generated-skill and SDD plan-link validation drift.

## Dependencies

- **Blocks:** [sase-bf.4](sase-bf.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bf.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bf.2/README.md) | [sase-bf.2](sase-bf.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@b49a17a`](https://github.com/sase-org/sase-core/commit/b49a17a4b038902064e2922b67b569ec9a761f55) | feat(agent-scan)!: preserve bounded JSON output variables | [sase-bf.2](sase-bf.2.md) | 2026-07-30 21:09:51 |
| sase | [`2b95bd3`](https://github.com/sase-org/sase/commit/2b95bd329fb0a8fa1b666b1019fed154b6870b7f) | feat(agent-scan): preserve structured output variables | [sase-bf.2](sase-bf.2.md) | 2026-07-30 21:46:05 |
