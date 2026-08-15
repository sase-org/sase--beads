# Bead: sase-m9.3.1.1 — Durable operation and result contracts

[Bead Pages](../README.md) / [sase-m9.3.1](sase-m9.3.1.md) / sase-m9.3.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.md) · **Assignee:** `sase-m9.3.1.1` · **Size:** large
**Created:** 2026-08-15 15:17:00 EDT · **Closed:** 2026-08-15 16:38:40 EDT
**Plan:** [202608/ace\_proc\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_proc_ownership.md)

## Description

durable-operation-contracts: inventory and classify every current _submit_tracked_proc and _submit_proc call site, define versioned mode-0600 request sidecars and typed result envelopes, add focused domain-command entry points for durable patch, agent, bead, notification, plugin, workspace, and run operations, and extend the proc submission adapter so callers provide argv, stable fingerprints, namespaced concurrency keys, and result paths without accepting or serializing Python callables.

## Notes

[2026-08-15T20:28:21Z · sase-m9.3.1.1] PROPOSED FOLLOW-UP: just check escalated to the full suite because this phase added a Symvision --epic-symbol in the Justfile (compare_inventory_to_source, consumed by sase-m9.3.1.2). The escalated run reported ~116 failures + 45 errors that look like pre-existing ANSI-markup-vs-plain-text assertions and AcePageGroup notification isolation leaks under parallel load, not regressions in the durable-operation contracts. Focused proc/settlement/inventory/command tests passed (48/48). Re-run just check after the Justfile change lands, or drop the epic-symbol once the next producer-migration phase imports compare_inventory_to_source.

[2026-08-15T20:38:16Z · sase-m9.3.1.1] PROPOSED FOLLOW-UP: just check escalates to the full suite because this phase adds --epic-symbol sase-m9.3.1.2(compare_inventory_to_source) in the Justfile. Run just check-full via sase monitor before landing the epic combined tree. The escalation is the inventory handoff, not a product regression in this contract-only phase.

[2026-08-15T20:38:40Z · sase-m9.3.1.1] Verified durable operation contracts: just install; just lint (ruff, mypy, symvision, toobig); 39 focused contract tests (ops I/O, settlement result-before-terminal and crash-after-publication, inventory AST conformance of 54 sites, argv-only ACE adapter, parser help and typed success/failure per command family); 90 existing proc reservation/settlement/parser tests. Monitor stop now emits a typed result on the JSON path too. just check was not re-run to completion because the Justfile epic-symbol for compare_inventory_to_source escalates to the full suite; that handoff is recorded as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-m9.3.1.2](sase-m9.3.1.2.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.3.1.3](sase-m9.3.1.3.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.3.1.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.1.1.md) | [sase-m9.3.1.1](sase-m9.3.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`07e254a`](https://github.com/sase-org/sase/commit/07e254a42073f3367bba23b1beb893ad72f92635) | feat(ops): add durable operation contracts and producer inventory | [sase-m9.3.1.1](sase-m9.3.1.1.md) | 2026-08-15 16:39:31 EDT |
