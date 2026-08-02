# Bead: sase-e8.1 — Scoped payload rows and stable payload ranking

[Bead Pages](../README.md) / [sase-e8](README.md) / sase-e8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ry](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ry/README.md) · **Assignee:** `sase-e8.1` · **Size:** medium
**Created:** 2026-08-02 14:04:05 UTC · **Closed:** 2026-08-02 14:19:52 UTC
**Plan:** [202608/commit\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_ref_completion.md)

## Description

core_menu: add `scope`, `rank`, and `body` to the at-reference payload row wire, match a qualified `scope@title` target so a repo fragment and subject words combine in one query, and make provider rank the tiebreak after tier and score so recency survives a typed query.

## Notes

[2026-08-02T14:19:08Z · sase-e8.1] PROPOSED FOLLOW-UP: Adopt provider rank for chat payload rows — chats are already recency-ordered and can opt into the new rank tiebreak without widening this epic.

[2026-08-02T14:19:52Z · sase-e8.1] Implemented backward-compatible scope/rank/body payload metadata, qualified scope-plus-title fuzzy matching with safe highlight mapping, malformed-scope fallback, and provider-rank tie-breaking in indexed and wire paths; verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

[2026-08-02T14:20:28Z · sase-e8.1] Implemented backward-compatible scope/rank/body payload metadata, qualified scope-plus-title fuzzy matching with safe highlight mapping, malformed-scope fallback, and provider-rank tie-breaking in indexed and wire paths; verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

[2026-08-02T14:22:15Z · sase-e8.1] Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and focused at-reference coverage; parent epic left open.

## Dependencies

- **Blocks:** [sase-e8.2](sase-e8.2.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e8.1/README.md) | [sase-e8.1](sase-e8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@c48c265`](https://github.com/sase-org/sase-core/commit/c48c26591d2dd5caaee743d9d4c83458a8684719) | feat(editor): support scoped at-reference payload ranking | [sase-e8.1](sase-e8.1.md) | 2026-08-02 14:25:22 |
