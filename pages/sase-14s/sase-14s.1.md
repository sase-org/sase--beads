# Bead: sase-14s.1 — Split crates/sase\_core\_py/src/lib.rs

[Bead Pages](../README.md) / [sase-14s](README.md) / sase-14s.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oh.md) · **Assignee:** `sase-14s.1` · **Size:** medium
**Created:** 2026-09-20 19:06:07 EDT · **Closed:** 2026-09-20 20:25:17 EDT
**Plan:** [202609/sase\_core\_big\_file\_split.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_big_file_split.md)

## Description

py_bindings: decompose the 35,166-line PyO3 binding crate root into a domain-keyed module tree while keeping the `sase_core_rs` pymodule registration intact.

## Notes

[2026-09-21T00:25:17Z · sase-14s.1] Split 35,166-line sase_core_py lib.rs into 26 domain dirs + prelude + test_support (60 files, all <=1500). Verified: 827 registrations before/after, 183 tests before/after, just check exit 0.

## Dependencies

- **Blocks:** [sase-14s.2](sase-14s.2.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14s.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.1/README.md) | [sase-14s.1](sase-14s.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@03036af`](https://github.com/sase-org/sase-core/commit/03036afdbf9b510550d3c60b6e08357ce939c992) | refactor(sase\_core\_py): split 35kloc lib.rs into domain module tree | [sase-14s.1](sase-14s.1.md) | 2026-09-20 20:27:04 EDT |
