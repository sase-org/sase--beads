# Bead: sase-i1.1 — Rust core regex matcher and fast-path flag

[Bead Pages](../README.md) / [sase-i1](README.md) / sase-i1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.w8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.w8/README.md) · **Assignee:** `sase-i1.1` · **Size:** medium
**Created:** 2026-08-09 07:41:19 EDT · **Closed:** 2026-08-09 07:55:58 EDT
**Plan:** [202608/bead\_search\_regex.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_search_regex.md)

## Description

core: add a shared bead query matcher to sase-core, thread an opt-in `regex` argument through `search_issues`/`search_issues_in_issues` and the `bead_search` PyO3 binding, teach the Rust bead CLI to parse `-e`/`--regex` and to highlight and snippet regex matches, and cover all of it with Rust tests.

## Notes

[2026-08-09T11:55:58Z · sase-i1.1] Implemented shared Rust bead query matcher, opt-in regex search flag/rendering, and PyO3 regex keyword support in sase-core; verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

[2026-08-09T11:57:21Z · sase-i1.1] Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace in linked sase-core

## Dependencies

- **Blocks:** [sase-i1.2](sase-i1.2.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.1/README.md) | [sase-i1.1](sase-i1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@721f20d`](https://github.com/sase-org/sase-core/commit/721f20d7710db7a53d622d1527d5be5d255c68b7) | feat(bead): add regex search support | [sase-i1.1](sase-i1.1.md) | 2026-08-09 08:08:48 EDT |
