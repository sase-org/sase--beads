# Bead: sase-1r5.1.3 — Adopt credential retries in the SDD store clone

[Bead Pages](../README.md) / [sase-1r5.1](sase-1r5.1.md) / sase-1r5.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1r5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.md) · **Assignee:** `sase-1r5.1.3` · **Size:** medium
**Created:** 2026-11-04 06:54:53 EST
**Plan:** [202611/github\_publickey\_retry.md](https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md)

## Description

sdd-clone-adopt: give `clone_sdd_store_to_path` a credential-retry budget separate from its transient schedule, using the launch budget, never holding the clone admission permit while sleeping. Prove it with an SSH-shim fake GitHub remote that denies N times and then serves a real bare repo.

## Dependencies

- **Depends on:** [sase-1r5.1.2](sase-1r5.1.2.md) ◐ · ⧖ 2026-11-04
- **Blocks:** [sase-1r5.1.5](sase-1r5.1.5.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r5.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r5.1.3/README.md) | [sase-1r5.1.3](sase-1r5.1.3.md) | 0 |
