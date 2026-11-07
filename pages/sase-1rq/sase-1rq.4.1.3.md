# Bead: sase-1rq.4.1.3 — Harden or quarantine the intermittent alias and card tests

[Bead Pages](../README.md) / [sase-1rq.4.1](sase-1rq.4.1.md) / sase-1rq.4.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) · **Assignee:** `sase-1rq.4.1.3` · **Size:** medium
**Created:** 2026-11-07 08:03:37 EST
**Plan:** [202611/bob\_mac\_capture\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_mac_capture_ci_green.md)

## Description

flakes: after alias-lane lands, classify each intermittently failing test: still failing, timing-sensitive (harden it), or a proven flake on an unchanged tree (quarantine it under the parent test_quarantine decision). Leave the suite with no known intermittent failures.

## Dependencies

- **Depends on:** [sase-1rq.4.1.1](sase-1rq.4.1.1.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.4.1.4](sase-1rq.4.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.4.1.3/README.md) | [sase-1rq.4.1.3](sase-1rq.4.1.3.md) | 0 |
