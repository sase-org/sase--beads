# Bead: sase-1pu.4 — Remove the full-check timeout for the empty-home SDD identity test (sase-120)

[Bead Pages](../README.md) / [sase-1pu](README.md) / sase-1pu.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.land.md) · **Assignee:** `sase-1pu.4` · **Size:** large
**Created:** 2026-10-29 19:19:01 EDT
**Plan:** [202610/task\_backlog\_epic\_3.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_3.md)

## Description

sdd-identity-check-flake: reproduce the repeated full-lane timeout and passing isolated run for test_sdd_git_identity_survives_empty_home_subprocess. Determine whether the nested subprocess or the temporary-directory leak guard causes the slow/failing result, then fix isolation or cleanup without weakening the test or simply extending its timeout. Verify the node, its file, and the scoped/full check.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.4.md) | [sase-1pu.4](sase-1pu.4.md) | 0 |
