# Bead: sase-1r5.1.4 — Adopt credential retries in SDD network git and workspace lease fetch

[Bead Pages](../README.md) / [sase-1r5.1](sase-1r5.1.md) / sase-1r5.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1r5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.md) · **Assignee:** `sase-1r5.1.4` · **Size:** medium
**Created:** 2026-11-04 06:54:53 EST
**Plan:** [202611/github\_publickey\_retry.md](https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md)

## Description

network-git-and-lease-adopt: route publickey denials in `run_sdd_network_git_with_retries` (agent publication) and the operational-lease `git fetch` through the shared tracker, replacing the lease's bespoke one-shot confirmation. Keep `is_credential_failure`, the ssh-agent hint, and the external mirror's `auth_error` label intact.

## Dependencies

- **Depends on:** [sase-1r5.1.2](sase-1r5.1.2.md) ✓ · ⧖ 2026-11-04
- **Blocks:** [sase-1r5.1.5](sase-1r5.1.5.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r5.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r5.1.4/README.md) | [sase-1r5.1.4](sase-1r5.1.4.md) | 0 |
