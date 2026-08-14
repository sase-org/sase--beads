# Bead: sase-lh.1 — Rename the Rust background-task core to procs

[Bead Pages](../README.md) / [sase-lh](README.md) / sase-lh.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.000](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.000.md) · **Assignee:** `sase-lh.1` · **Size:** medium
**Created:** 2026-08-13 17:18:54 EDT · **Closed:** 2026-08-13 17:45:35 EDT
**Plan:** [202608/background\_tasks\_to\_procs.md](https://github.com/sase-org/sase--plans/blob/main/202608/background_tasks_to_procs.md)

## Description

core: rename `crates/sase_core/src/tasks/` to `procs/` in ../sase-core, rename the wire structs and the `task_id` field to `Proc*`/`proc_id`, bump the wire schema to 2 while still deserializing legacy `task_id` records, and expose canonical `read_procs_snapshot`/`append_proc`/`update_proc`/`prune_procs` PyO3 bindings alongside the existing legacy binding names.

## Notes

[2026-08-13T21:43:57Z · sase-lh.1] PROPOSED FOLLOW-UP: Fix unrelated mypy failure in LLM subprocess compatibility exports — just check fails because src/sase/llm_provider/_subprocess.py imports stream_and_parse_messages_json_output from _subprocess_claude, but that module only exposes _stream_and_parse_messages_json_output/stream_and_parse_json_output.

[2026-08-13T21:45:35Z · sase-lh.1] Verified cargo fmt --all -- --check, cargo test, cargo clippy --all-targets -- -D warnings in linked sase-core; from sase workspace verified just install, just rust-install, and a Python binding smoke test for canonical proc bindings plus legacy task aliases. Ran just check, but it failed on an unrelated existing mypy error in src/sase/llm_provider/_subprocess.py; recorded a PROPOSED FOLLOW-UP note on this phase bead.

[2026-08-13T21:47:46Z · sase-lh.1] Verified cargo fmt --all -- --check, cargo test, cargo clippy --all-targets -- -D warnings, just install, just rust-install, and Python binding smoke test; just check hit unrelated mypy issue recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-lh.2](sase-lh.2.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lh.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.1/README.md) | [sase-lh.1](sase-lh.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c69a2f8`](https://github.com/sase-org/sase-core/commit/c69a2f885b327f92c55687defd23c577dfe74f70) | feat(core)!: rename background task core to procs | [sase-lh.1](sase-lh.1.md) | 2026-08-13 18:02:21 EDT |
