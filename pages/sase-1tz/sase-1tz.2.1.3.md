# Bead: sase-1tz.2.1.3 — Turn repeated publication failures into standing alerts with backoff

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.3` · **Size:** medium
**Created:** 2026-11-19 11:13:26 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

pub_standing: a sase-core decider keys publication failures by (project, signature) and reports only opened, changed, escalated, and cleared transitions. It backs off project-scoped failures. A standing store keeps true attempt counts and first/last-seen times, and one notification per alert fires only on transitions.

## Dependencies

- **Depends on:** [sase-1tz.2.1.1](sase-1tz.2.1.1.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.5](sase-1tz.2.1.5.md) ◐ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.7](sase-1tz.2.1.7.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.3/README.md) | [sase-1tz.2.1.3](sase-1tz.2.1.3.md) | 0 |
