# Bead: sase-yy.8.6.1 — Restore the required core revision baseline

[Bead Pages](../README.md) / [sase-yy.8.6](sase-yy.8.6.md) / sase-yy.8.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yy.8.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.8.land.md) · **Assignee:** `sase-yy.8.6.1` · **Size:** small
**Created:** 2026-09-11 06:54:38 EDT · **Closed:** 2026-09-11 07:25:26 EDT
**Plan:** [202609/artifact\_link\_durable\_truth\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_durable_truth_repairs.md)

## Description

binding_baseline: ratchet the core revision to include existing projection and cutover APIs and verify the exact pinned build.

## Notes

[2026-09-11T11:24:54Z · sase-yy.8.6.1] PROPOSED FOLLOW-UP: Restore whole-repo verification green after the core-pin baseline - just check is currently blocked by pre-existing feature-flag lint for live bead sase-z6/ace_unified_agents, and the core-identity-triggered full pytest lane reported 33 failures outside this phase after 40549 passes.

[2026-09-11T11:25:26Z · sase-yy.8.6.1] Ratchet applied with tools/ratchet_core_revision: sase-core-revision.txt now pins cd9864ead8d3b4500022e6805fd044f22bf7c412, containing required 717c36e and e0f105d APIs and advancing beyond the 3e32c5cc6 lineage-wire pin. Verified just ratchet-core-revision --check, exact pinned checkout install via just rust-install, tools/validate_sase_core_rs --sase-core-dir sase/repos/linked/sase-core, and tools/check_sase_core_rs_bindings (545 bindings). Also ran just check, which failed in unrelated feature-flag lint for live bead sase-z6/ace_unified_agents; direct test-scoped escalated for core identity and completed 40549 passed, 33 failed, 13 skipped. No epic symbols remained.

## Dependencies

- **Blocks:** [sase-yy.8.6.2](sase-yy.8.6.2.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-yy.8.6.5](sase-yy.8.6.5.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-yy.8.6.6](sase-yy.8.6.6.md) ◐ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.8.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yy.8.6.1/README.md) | [sase-yy.8.6.1](sase-yy.8.6.1.md) | 0 |
