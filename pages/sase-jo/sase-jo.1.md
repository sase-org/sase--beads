# Bead: sase-jo.1 — Core stitch-origin classifier

[Bead Pages](../README.md) / [sase-jo](README.md) / sase-jo.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xv](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xv/README.md) · **Assignee:** `sase-jo.1` · **Size:** medium
**Created:** 2026-08-11 06:57:58 EDT · **Closed:** 2026-08-11 07:13:21 EDT
**Plan:** [202608/stitch\_origin\_badges.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_origin_badges.md)

## Description

core: add the `CommitOriginWire` enum, the footer-driven `classify_commit_origin` function, and the `origin` field on the VCS-log commit wire in the linked `sase-core` repo, bump the VCS-log wire schema version, and expose both through the PyO3 binding with Rust unit and parity tests.

## Notes

[2026-08-11T11:13:21Z · sase-jo.1] Implemented CommitOriginWire/classify_commit_origin in sase-core, populated VCS-log origin, bumped schema to 4, exposed PyO3 classify_commit_origin and origin dict field; verified with cargo fmt --all, cargo test -p sase_core vcs_log, cargo test -p sase_core --test vcs_log_parity, and cargo test -p sase_core_py --lib.

[2026-08-11T11:15:37Z · sase-jo.1] Verified cargo fmt --all, cargo test -p sase_core vcs_log, cargo test -p sase_core --test vcs_log_parity, and cargo test -p sase_core_py --lib

## Dependencies

- **Blocks:** [sase-jo.3](sase-jo.3.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jo.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jo.1/README.md) | [sase-jo.1](sase-jo.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@dc836c4`](https://github.com/sase-org/sase-core/commit/dc836c491b175694563baba60f52ba839feb0e30) | feat(vcs-log): classify commit origins | [sase-jo.1](sase-jo.1.md) | 2026-08-11 07:21:57 EDT |
