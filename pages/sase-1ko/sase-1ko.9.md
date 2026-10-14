# Bead: sase-1ko.9 — Grok full-bundle rules and Muse prompt-prefix delivery

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.9` · **Size:** medium
**Created:** 2026-10-13 18:10:37 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

grok-muse: create the `grok_explicit_instructions` sunset flag, plus `muse_explicit_instructions` if the Muse spike passed. Grok's `--rules` carries the full root bundle, and memory v2 is set per decision. Muse gets the bundle as its prompt prefix without `--trust-workspace`, or is declared legacy with no flag. Interrupt and wait reconstruction never nests a second bundle.

## Dependencies

- **Depends on:** [sase-1ko.1](sase-1ko.1.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.10](sase-1ko.10.md) ◐ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.5](sase-1ko.5.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.6](sase-1ko.6.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.9/README.md) | [sase-1ko.9](sase-1ko.9.md) | 0 |
