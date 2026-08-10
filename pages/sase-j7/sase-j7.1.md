# Bead: sase-j7.1 — Fix the confirmed xprompt VCS-tag cache leak

[Bead Pages](../README.md) / [sase-j7](README.md) / sase-j7.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-j0.w1.f0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j0.w1.f0/README.md) · **Assignee:** `sase-j7.1` · **Size:** medium
**Created:** 2026-08-10 15:44:32 EDT
**Plan:** [202608/fix\_sase\_ct\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/fix_sase_ct_flake_class.md)

## Description

vcs-cache - give the caches derived from workspace-provider metadata a real invalidation entry point and restore them on teardown, so a test that fakes plugin metadata stops poisoning every later test in its worker.

## Dependencies

- **Blocks:** [sase-j7.4](sase-j7.4.md) ◐ · ⧖ 2026-08-10
- **Blocks:** [sase-j7.5](sase-j7.5.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j7.1/README.md) | [sase-j7.1](sase-j7.1.md) | 0 |
