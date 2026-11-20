# Bead: sase-1tz.3.1.2 — Build an update-overlap reproducer for jobs, launches, and native code

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.2` · **Size:** medium
**Created:** 2026-11-20 09:19:05 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

swap_repro: a test-only harness simulates an install swap in temp dirs under a real code-swap writer lock. It drives vanishing scripts, a vanishing binding, mixed-version lazy imports, and in-place versus atomic file replacement. Still-failing modes become strict xfails for the guard phases. Record which modes reproduce and how the real installers replace files.

## Dependencies

- **Blocks:** [sase-1tz.3.1.3](sase-1tz.3.1.3.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.2/README.md) | [sase-1tz.3.1.2](sase-1tz.3.1.2.md) | 0 |
