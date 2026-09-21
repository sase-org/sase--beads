# Bead: sase-14s.10 — Split crates/sase\_gateway/src/sudo\_runner.rs

[Bead Pages](../README.md) / [sase-14s](README.md) / sase-14s.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oh.md) · **Assignee:** `sase-14s.10` · **Size:** medium
**Created:** 2026-09-20 19:06:19 EDT · **Closed:** 2026-09-21 11:19:03 EDT
**Plan:** [202609/sase\_core\_big\_file\_split.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_big_file_split.md)

## Description

sudo_runner: decompose the 4,595-line gateway sudo runner into a sudo_runner/ module tree and close out the epic's file-size invariant.

## Notes

[2026-09-21T15:17:48Z · sase-14s.10] PROPOSED FOLLOW-UP: sudo_runner apt_get_shaped cwd test flaked once with ETXTBSY on fake-sudo exec under parallel run; passed alone and on full re-run — consider serializing fixture script exec or retry

[2026-09-21T15:19:03Z · sase-14s.10] Split 4683-line sudo_runner.rs into sudo_runner/ tree (max file 701 lines); 46 tests preserved (45 run on linux, 1 non-linux-gated); public API unchanged via mod.rs re-exports; just check (check.sh all) exit 0; repo-wide >1500 audit shows only untargeted files

## Dependencies

- **Depends on:** [sase-14s.9](sase-14s.9.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14s.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.10/README.md) | [sase-14s.10](sase-14s.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@5154900`](https://github.com/sase-org/sase-core/commit/51549000a1cfa59e4b6806a39ed5595bba93dde1) | refactor(sase\_gateway): split sudo\_runner.rs into \<=701-line module tree | [sase-14s.10](sase-14s.10.md) | 2026-09-21 11:29:34 EDT |
