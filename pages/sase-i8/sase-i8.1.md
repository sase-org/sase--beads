# Bead: sase-i8.1 — Rust core — parent ids, tolerant parser, merge summary

[Bead Pages](../README.md) / [sase-i8](README.md) / sase-i8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wl/README.md) · **Assignee:** `sase-i8.1` · **Size:** medium
**Created:** 2026-08-09 09:43:09 EDT · **Closed:** 2026-08-09 10:07:16 EDT
**Plan:** [202608/merge\_commit\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_commit_support.md)

## Description

core: in the sase-core repo, add parent ids to the VCS-log wire, make the pinned git-log parser accept both the legacy 7-field and the new 8-field record layout, bump the wire schema to 3, add a strict merge-subject summary parser, and expose the new PyO3 bindings.

## Notes

[2026-08-09T14:07:16Z · sase-i8.1] Implemented sase-core VCS-log schema 3 parent_ids, tolerant 7/8-field parser, strict merge-summary parser, and PyO3 schema/summary bindings; verified cargo fmt --all -- --check, cargo test --workspace, cargo clippy --workspace --all-targets -- -D warnings, cargo test -p sase_core vcs_log, cargo test -p sase_core --test vcs_log_parity, and cargo test -p sase_core_py --lib binding.

[2026-08-09T14:13:10Z · sase-i8.1] Verified cargo fmt --all -- --check; cargo test -p sase_core vcs_log; cargo test -p sase_core --test vcs_log_parity; cargo test -p sase_core_py vcs_log_binding_exposes_schema_and_parent_ids; cargo test -p sase_core_py parse_merge_summary_binding_returns_dict_or_none; cargo clippy --workspace --all-targets -- -D warnings; git diff --check.

## Dependencies

- **Blocks:** [sase-i8.2](sase-i8.2.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.1/README.md) | [sase-i8.1](sase-i8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@459bbc6`](https://github.com/sase-org/sase-core/commit/459bbc68f3393739969d83a729eaeadb5b32fc6a) | feat(vcs-log): add parent ids and merge summaries | [sase-i8.1](sase-i8.1.md) | 2026-08-09 10:14:02 EDT |
