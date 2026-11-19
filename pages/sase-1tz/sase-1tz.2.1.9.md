# Bead: sase-1tz.2.1.9 — Stop policy-initiated garbage collections from blocking the loop for seconds

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.9` · **Size:** medium
**Created:** 2026-11-19 11:13:28 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

gc_policy: idle, backstop, and RSS-backstop collections stay bounded. The policy re-freezes survivors, defers full collections while the process is swapping, and cost-gates the backstops, while keeping the memory backstops. Before/after pause stats are recorded by trigger.

## Dependencies

- **Blocks:** [sase-1tz.2.1.10](sase-1tz.2.1.10.md) ◐ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.13](sase-1tz.2.1.13.md) ◐ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.8](sase-1tz.2.1.8.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.9/README.md) | [sase-1tz.2.1.9](sase-1tz.2.1.9.md) | 0 |
