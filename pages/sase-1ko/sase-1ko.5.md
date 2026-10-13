# Bead: sase-1ko.5 — Delivery-plan hook, active delivery, atomic legacy fallback, and helper manifests at the boundary

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.5` · **Size:** medium
**Created:** 2026-10-13 18:10:35 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

delivery-plan: add the `llm_instruction_delivery` hookspec and the DeliveryPlan model, with declared-legacy built-ins. The boundary resolves the plan, renders the root bundle and (when declared) the helper bundle, validates transport, writes v2 manifests, and exposes the active delivery to adapters. It records session ids and falls back atomically to legacy delivery with a deduplicated notification. Bundle files become 0644.

## Dependencies

- **Depends on:** [sase-1ko.2](sase-1ko.2.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.6](sase-1ko.6.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.7](sase-1ko.7.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.8](sase-1ko.8.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.9](sase-1ko.9.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.5/README.md) | [sase-1ko.5](sase-1ko.5.md) | 0 |
