# Bead: sase-9z.1 — Canonical plans reference scheme in the Rust core

[Bead Pages](../README.md) / [sase-9z](README.md) / sase-9z.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9z.1` · **Size:** medium
**Created:** 2026-07-27 12:39:15 UTC
**Plan:** [202607/durable\_plan\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/durable_plan_refs.md)

## Description

refs: add the parse/render/resolve API for `plans:` references to the Rust core, expose it through the PyO3 binding, and give the Python side one root-resolution facade that also accepts every legacy path form.

## Dependencies

- **Blocks:** [sase-9z.2](sase-9z.2.md) ✓
- **Blocks:** [sase-9z.3](sase-9z.3.md) ✓
- **Blocks:** [sase-9z.4](sase-9z.4.md) ✓
- **Blocks:** [sase-9z.5](sase-9z.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9z.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9z.1/README.md) | [sase-9z.1](sase-9z.1.md) | 2 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@1136e72`](https://github.com/sase-org/sase-core/commit/1136e7288cc3d40929201127bb12c7e5853001bd) | feat(plan): add durable plan reference contract (sase-9z.1) | [sase-9z.1](sase-9z.1.md) | 2026-07-27 13:16:46 |
| [`6065356`](https://github.com/sase-org/sase/commit/6065356e7beacd1dfd452b081ad093a0894afe99) | feat(sdd): add shared plan reference facade (sase-9z.1) | [sase-9z.1](sase-9z.1.md) | 2026-07-27 13:17:41 |
