# Bead: sase-rn.5 — Isolated plugin and configuration finalizer execution

[Bead Pages](../README.md) / [sase-rn](README.md) / sase-rn.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08y.md) · **Assignee:** `sase-rn.5` · **Size:** medium
**Created:** 2026-08-20 16:35:05 EDT
**Plan:** [202608/pluggable\_finalizers.md](https://github.com/sase-org/sase--plans/blob/main/202608/pluggable_finalizers.md)

## Description

extension-runtime: implement the `sase_finalizers` subprocess protocol with sanitized environments and bounded JSON I/O, add constrained `builtin@command`, surface activation and provenance through `sase final list`, `show`, and `doctor`, and prove with a non-mutating reference plugin that installation alone never activates behavior.

## Dependencies

- **Depends on:** [sase-rn.3](sase-rn.3.md) ◐ · ⧖ 2026-08-20
- **Blocks:** [sase-rn.6](sase-rn.6.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rn.5/README.md) | [sase-rn.5](sase-rn.5.md) | 0 |
