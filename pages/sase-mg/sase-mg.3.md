# Bead: sase-mg.3 — Add the variable selector language and get command

[Bead Pages](../README.md) / [sase-mg](README.md) / sase-mg.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02u.md) · **Assignee:** `sase-mg.3` · **Size:** medium
**Created:** 2026-08-15 15:37:08 EDT · **Closed:** 2026-08-15 18:02:36 EDT
**Plan:** [202608/powerful\_variables.md](https://github.com/sase-org/sase--plans/blob/main/202608/powerful_variables.md)

## Description

selector-get-cli: implement exact, global, hood, key-wildcard, and JSON-path selectors with predictable output for humans, shells, and agents.

## Notes

[2026-08-15T22:01:30Z · sase-mg.3] PROPOSED FOLLOW-UP: provider-disable smoke still fails on isolated HOME — tests/llm_provider/test_provider_disable_smoke.py::test_provider_disable_fresh_process_smoke_matrix raises StopIteration looking for alias medium_worker after set_alias_override("medium_worker", ...); reproduces on this tree without touching llm_provider, likely stale now that doctor tells users to use @medium instead

[2026-08-15T22:02:36Z · sase-mg.3] Added Rust selector AST/parser/resolution (exact, global, hood, key-wildcard, JSON-path) plus sase var get with pretty/raw/json/jsonl. Verified: sase-core clippy -D warnings; 10 selector unit tests; Python parser/handler/wire tests for dotted/hyphenated/digit names, hood root, wildcards, dedup, path errors, raw single-value, limits, hidden/project filters; just check lint green; escalated full suite 30508 passed / 1 unrelated provider-disable smoke failure recorded as PROPOSED FOLLOW-UP.

[2026-08-15T22:04:32Z · sase-mg.3] Added Rust selector AST/parser/resolution (exact, global, hood, key-wildcard, JSON-path) plus sase var get with pretty/raw/json/jsonl. Verified: sase-core clippy -D warnings; 10 selector unit tests; Python parser/handler/wire tests for dotted/hyphenated/digit names, hood root, wildcards, dedup, path errors, raw single-value, limits, hidden/project filters; just check lint green; escalated full suite 30508 passed / 1 unrelated provider-disable smoke failure recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-mg.2](sase-mg.2.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mg.4](sase-mg.4.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mg.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mg.3/README.md) | [sase-mg.3](sase-mg.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@13a9db1`](https://github.com/sase-org/sase-core/commit/13a9db10c78e19c8e3aea45412999dd741fc206b) | feat: parse and resolve output-variable selectors | [sase-mg.3](sase-mg.3.md) | 2026-08-15 18:06:25 EDT |
| sase | [`3b81003`](https://github.com/sase-org/sase/commit/3b810036f1a5b864f0e2641d8ede4d847cd01855) | feat(var): add selector language and get command | [sase-mg.3](sase-mg.3.md) | 2026-08-15 18:07:32 EDT |
