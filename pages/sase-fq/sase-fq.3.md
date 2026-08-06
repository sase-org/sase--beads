# Bead: sase-fq.3 — Configure a git identity on the sidecar clone in the git-sync fixtures

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tq/README.md) · **Assignee:** `sase-fq.3` · **Size:** small
**Created:** 2026-08-05 21:05:50 EDT · **Closed:** 2026-08-05 21:18:23 EDT
**Plan:** [202608/ci\_master\_red\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_master_red_recovery.md)

## Description

sidecar-git-identity: set user.name/user.email on the sidecar clone built by setup_repo so tests that commit there stop failing with exit 128 on runners where git cannot auto-detect an identity.

## Notes

[2026-08-06T01:18:23Z · sase-fq.3] Set user.name/user.email on the sidecar clone in tests/agents_sync/git_sync_fixtures.py::setup_repo, matching the seed repo's existing identity config. Confirmed remote/seed/sidecar are the only repos this module creates, and seed already had an identity, so no other spot needed the same treatment. Verified: reproduced the exit-128 failure pre-fix under an environment where git cannot auto-detect an identity (HOME=mktemp, GIT_CONFIG_GLOBAL/SYSTEM=/dev/null, user.useConfigOnly=true), confirmed it clears post-fix, and reran the full tests/agents_sync suite (242 passed) under that same blocked-identity environment.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.3/README.md) | [sase-fq.3](sase-fq.3.md) | 0 |
