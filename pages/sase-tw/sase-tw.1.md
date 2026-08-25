# Bead: sase-tw.1 — A rebuild may delete only what it can prove was deleted

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.1` · **Size:** medium
**Created:** 2026-08-25 15:34:35 EDT · **Closed:** 2026-08-25 16:01:02 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

index-durability: make `preview_aggregate` carry forward prior rows whose owning companion is not visible in this workspace, make `link rm` prune the aggregate unconditionally, add a cross-workspace reconciliation sweep gated on agent publication, and add doctor counters that make future index divergence loud.

## Notes

[2026-08-25T20:01:02Z · sase-tw.1] Implemented conservative artifact-link aggregate rebuilds, unconditional aggregate pruning for link removal, cross-workspace reconciliation for artifact doctor --fix with published-agent gating, and doctor divergence counters; verified with targeted pytest and just check.

## Dependencies

- **Blocks:** [sase-tw.11](sase-tw.11.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.13](sase-tw.13.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.2](sase-tw.2.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.3](sase-tw.3.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.4](sase-tw.4.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.1/README.md) | [sase-tw.1](sase-tw.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e46adb7`](https://github.com/sase-org/sase/commit/e46adb77f14965dd49d680f35618e1b92b36a1cf) | fix(artifact-links): preserve aggregate rows across workspace rebuilds | [sase-tw.1](sase-tw.1.md) | 2026-08-25 16:02:32 EDT |
